# Tasks of the Software Designers

The non limiting list of tasks of the software designers is:

* **Game Creator Engine**: software modules to create variants of \(city\) games. By means of a configuration file it should be possible to upgrade, modify or configure the embedded system firmware in the game box. The suggested format of the configuration file is a JSON \(Javascript Object Notation\) based data-interchange format.
* **Visualization Software**: a Graphical User Interface \(GUI\) should be able to visualize the global status of the game, update the gameplay, summarize the status of the individual, competing teams, communicate with the individual teams, ... This software module acts as a kind of dispatching center for the game master.
* **Database Management System**:  a database should be maintained, interfaced, updated, secured. All database transactions should be handled by this software module.
* **Media Web Server**: a Web Server should be able to collect and process media information, files, ... of the competing teams. Photos from a smartphone or tablet PC could be uploaded to the server. A File Management System or Content Management System could be valuable suggestions.
* **Game Management System**: this is the centralized, top level software framework, that integrates seamlessly all the above mentioned software modules. A programming language that supports Object Oriented Programming, multi-threading, ... is mandatory. The Game Management System should be able to interface a database, visualize the status of the gameplay, process web content and media, interact with the game master, communicate with the competing teams, validate and process the results of the teams, ... 

The **Unified Modeling Language** \(UML\) methodology could be very useful to manage, design and maintain the global and partial parts of the software project \(see **Figure 10**\). In a transparant and clear manner the structure \(attributes and behavior\) and relations between classes is visualized. This is a rather powerful tool for supporting the process of software development.

![an example of UML software modelling](/assets/UML_class_diagram_hotel-949x683.png)

![Engineering quote](/assets/Engineering-quote-6.jpg)

