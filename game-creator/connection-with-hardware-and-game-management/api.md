# API

* ### What is API

An application programming interface, also known as API, combines protocols, tools and a set of subroutine definitions. API makes it possible for aan app or computersystem to interchange information with the outside world. API's aren't a new feature at all, they are to be found in every pc. Without API we wouldn't be able to copy and paste text from a word document into an e-mail and so on.

All of this is possible because API shares a very limited information about the sending program's internal functions to the outside world. Because of this the application can share data and they can take actions on each others behalf without developpers requiring to share all their software's code.

The most important thing about APIs is that the user doesn't even need to know it's there. When the user for instance sends data via an application, he doesn't want to be confronted with all kinds of tedious tasks, he only wants to quikly send data and maybe know if it arrived.

* ### Most important APIs

APIs between software libraries are something we need on a daily basis, copy and pasting for instance would be impossible without this. it allows a seperation from its implementation so that programs written in one language can use libraries written in another.

There are also** System-level APIs** which make it possible for an application like LibreOffice or Word to run on an OS like windows. The Windows API is well known for being backwards compatible, so older applications will still work on newer versions of windows by putting it in the "Compatibility mode."

We ** **encounter** Web APIs **on a daily basis, if you go to a site which for example has a little google maps map with a marker where the store is located, all of this is made possible with Web APIs. It's really hard, even almost impossible, to find a website which doesn't make use of any Web APIs. It makes for way better and more user friendly sites.

* ### Problems with API

Because you are dependent on someone else, API isn't perfect. If the company you are dependent on suddenly decides to shutdown you are left with nothing and the application at your end will lose some functionality. So you have to keep in mind that the fact that you have a working API now, that might not be the case anymore in a few years depending on the place where you share/get data from.

* ### How did we use API in the VIVES City Game project

We thought it would be way better if the user could just send the json file to the Game Management in stead of having to use a usb stick or something like that so we decided to implement API inside our project. For creating our google maps, we also relied on an API, this will be further explained in chapter **GmapsFX**.

Because java doesn't have API build in we had to rely on some prebuild packages. We chose OkHttp, OkHttp is an HTTP client for Android and Java applications with high speed and low bandwidth use. OkHttp also makes use of OkIO, this adds fast I/O and resizable buffers. With these 2 libraries we are able to create a simple class that stages our JSON file to be send to the Game Management.

![](/assets/OkHttp.png)

With this class in place, the only thing left is to create a button that allows the Json file to be send. This button is very basic and just adds the JSON file and a URL where the JSON file will be send to.

![](/assets/upload.png)

* ### Problems encountered

In implementing OkHttp inside our project we encountered some small problems. Because we worked with a Maven Project, we couldn't simply drag and drop the necessary libraries into the project. Luckily OkHttp provided a piece of code we could add to our pom.xml file which automaticaly added all the necessary packages.

![](/assets/OkHttp2.png)

### 



