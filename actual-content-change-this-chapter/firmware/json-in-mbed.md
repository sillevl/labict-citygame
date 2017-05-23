## JSON in mbed

#### Introduction

From the **game creators** we will receive a JSON file. The **FRDM-K64F Development Board** needs to read this JSON file. Standard in mbed this isn't implemented so we need to do some research about this. We found a library that we could use in our program to accomplish this task.

#### Library MbedJSONValue

The library we used, called **MbedJSONValue**. Here you can find the documentation of the library: [MbedJSONValue](https://developer.mbed.org/users/samux/code/MbedJSONValue/docs/tip/classMbedJSONValue.html).

#### First Approach

First of all we tested this library with a piece of our JSON file. Below you can see the program:

```cpp
#include <iostream>
#include "mbed.h"
#include "MbedJSONValue.h"

int main()
{
    MbedJSONValue demo;

    const char * json = "{\"name\":\"LocationGame\",\"box_description\":\"Go to locations.\",\"full_description\":\"Whilst bringing the rebels to the imperial prison, your stardestroyer got shot. Retrieve the lost communicator parts to contact an extraction team\",\"length\":3000,\"time\":120,\"missions\":[{\"id\":1,\"name\":\"GotoLocation\",\"description\":\"The first part is at the entrance of Kinepolis\",\"locations\":[{\"lat\":51.223142,\"long\":2.896536,\"radius\":20.3}]},{\"id\":2,\"name\":\"GotoLocation\",\"description\":\"The next one is at the Spar\",\"locations\":[{\"lat\":51.222359,\"long\":2.892109,\"radius\":15.5}]}]}";

    // parse the previous string and fill the object demo
    parse(demo, json);

    std::string name;
    std::string box_description;
    std::string full_description;
    int length;
    int my_time;
    int id;
    std::string mission_name;

    // put the JSON file values in the variables
    name = demo["name"].get<std::string>();
    box_description = demo["box_description"].get<std::string>();
    full_description = demo["full_description"].get<std::string>();
    length = demo["length"].get<int>();
    my_time = demo["time"].get<int>();
    id = demo["missions"][0]["id"].get<int>();
    mission_name = demo["missions"][0]["name"].get<std::string>();

    // printing the values
    printf("Name: %s\r\n", name.c_str());
    printf("Box_description: %s\r\n", box_description.c_str());
    printf("Full_description: %s\r\n", full_description.c_str());
    printf("Length: %d\r\n", length);
    printf("Time: %d\r\n", my_time);
    printf("MissionId: %d\r\n", id);
    printf("MissionName: %s\r\n", mission_name.c_str());
}
```

#### Object Oriented Programming

Of course we need to make the program **Object Oriented**. **Object Oriented Programming `(OOP)`** is a programming paradigm based on the concepts of **objects**, which may contain **data**, in the form of fields, often known as **attributes**, and **code** in the form of procedures, often known as **methods**.

With that been said, we need to create for example a **Mission class** that should give us all the values that are being stored in the **missions array** from that JSON file.