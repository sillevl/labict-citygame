## I²C

#### Introduction

The name I²C is shorthand for **Standard Inter-Integrated Circuit** bus. I²C is a serial data protocol which operates with a **master/slave relationship**. I²C only uses **two physical wires**, this means that data only travels in one direction at a time.

The I²C communication signals are **serial data `(SDA)`** and **serial clock `(SCL)`**:
* These two signals make it possible to **support serial communication** of 8 bit data bytes, 7 bit device addresses as well as control bits
* Using just two wires makes it **cheap and simple to implement in hardware**

![](/assets/I2C.JPG)

#### Using I²C in our project

It is very useful if you can get the amount of voltage of the battery. We used I²C to accomplish this feature. In the following topics I will give some examples of our program that we made to realize this. The whole program you can find [here](http://git.labict.be/alexvancoillie/City_Game_I2C) on this link. If you want to go immediately to the files of the project, click on this link: [files](http://git.labict.be/alexvancoillie/City_Game_I2C/tree/master).

#### Datasheet of the ADC081

Every topic that I will describe is based on this IC.
This is the datasheet of the IC we used in our project:
[Datasheet ADC081](http://www.ti.com/lit/ds/symlink/adc081c027.pdf).

In the datasheet you will find the following information:
* Manufacturer's name
* Product number and name
* Notable device properties
* **Pin connection diagram**
* **Pin descriptions**
* Block diagram
* **Absolute minimum and maximum ratings**
* Characteristics
* Timing diagram
* Specification definitions
* Typical performance characteristics
* Functional description
* **Internal registers**
* Applications information

To write a I²C program, you only need the **Internal registers** topic of the datasheet. If you want to test the program you should read the following topics:
* **Pin connection diagram**
* **Pin descriptions**
* **Absolute minimum and maximum ratings**

#### I²C address

###### Theoretical

The I²C address of the slave is always a 7 bit address. The I²C 7 bit address should then be given a MSB justified byte data. For instance, if the slave device has address of `1100000` (7 bit binary), it should be given as `0xC0`. You are just doing a **1 bit left shift operation**. In binary it would look like this `11000000`. In this notation, the LSB doesn't need to be cared. The 8th bit after the 7 bit slave address should be read or write bit and it is provided (overwritten) by mbed SDK (inside of the `write()` function).

###### Practical

The I²C address can be found in the datasheet, it depends on the fact how you connect the IC. In this project we connected the pin `ADDR` to the `ground`.

![](/assets/I2C address.JPG)

#### Registers

###### Address Pointer Register

The **address pointer** determines which of the data registers is accessed by the I²C interface. The first data byte of every write operation is stored in the address pointer register. This value selects the register that the following data bytes will be written to or read from. Only the three LSBs (Least Significant Bits) of this register are variable. The three **Least Significant Bits** are the three first bits on the right side. The other bits must always be written to as zeros. After a power-on reset, the pointer register defaults to all zeros, this is **equal to the pointer address** of the **Conversion Result Register**.

![](/assets/address_pointer_register.JPG)

###### Configuration Register

In our project we do not need the configuration register, but I wanted to implement it in the library, to make it more user friendly. With this register you can **change the configurations** of the IC.

![](/assets/configuration_register_1.JPG)
![](/assets/configuration_register_2.JPG)

###### Conversion Result Register

This register holds the result of the most recent conversion. In the normal mode, a new conversion is started whenever this register is read. As you can see in the image below, the **conversion result** is just **from bit D4 until bit D11**. So we must **filter these 2 bytes** in order to get the result. In the following topics, I will give you more information about how to do this.

![](/assets/conversion_result_register.JPG)

#### Write

The I²C class has a `write()` function and this function will send the I²C address and data on I²C bus.

The `write()` function takes 4 arguments:
* **slave_address**
* **pointer to an array**
* **length of the array**
* **repeat (default = false)**

With those parameters, the mbed SDK (Software Development Kit) manages multiple bytes transfer automatically. The function will be returned when the transfer has been completed.

This is an example of a `write()` function in my code:

```cpp
void ADC081::config(char conf)
{
    cmd[0] = 0x02; // pointer to configuration register
    cmd[1] = conf; // the wanted configuration
    i2c.write(ADDR, cmd, 2); // send command string
}
```

#### Read

To read a register, it needs to be **done by two I²C transfers**:
* The first transfer is a `write()` function to **specify the register address**.
* The second transfer is a `read()` function and this function **will read from the register**.

The `read()` function takes 4 arguments:
* **slave_address**
* **pointer to an array**
* **length of the array**
* **repeat (default = false)**

This is an example of a `read()` function in my code:

```cpp
double ADC081::readConversionResult()
{
    cmd[0] = 0x00; // set pointer to conversion result register
    i2c.write(ADDR, cmd, 1); // define which register you want to read
    i2c.read(ADDR, cmd, 2); // read the two-byte echo result
}
```

#### Conversion

After the `read()` function, we will need to filter the received two-byte result from the **conversion result register**.

In the program below you can see how we did this:

```cpp
void ADC081::printValue()
{
    readConversionResult();
    // echo will store the conversion result
    echo = ((cmd[0] << 4) + (cmd[1] >> 4));
    // to make sure the program would not crash if it divides by zero
    if(echo != 0)
    {
        percentage = (((float)echo)/2.55);
        voltage = percentage * 0.033;
    }
    else
    {
        cout << "ECHO = 0\r\n" << endl;
    }
    printf("0: %02X 1: %02X echo: %02X\r\n", (cmd[0] << 4), (cmd[1] >> 4), ((cmd[0] << 4) + (cmd[1] >> 4)));
    std::cout << "Percentage: " << percentage << "\r\n" << std::endl;
    std::cout << "Voltage: " << voltage << "\r\n" << std::endl;
    wait(0.8);
}
```

#### Testing I²C

Before you get started, keep in mind that you will need to provide a pull up resistor for the **serial data `(SDA)`** line and also for the **serial clock `(SCL)`** line. Both of these resistors must have a power supply.