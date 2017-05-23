### **Keys**
![](/assets/Editgames.png)
If you clicked on edit games you will see the following screen appear.
![](/assets/editpage.png)
You'll see the keys on your left side.
The keys are randomly generated.
They are linked with each accepted game, so every game has their unique set of keys for teams and the gamemaster.
The keys are generated when you choose a scenario and if you link the mbed to the teamnames provided by the teams.
After this they are inserted into the login collection, together with the function of the keys(team or master).


### **UML**
Login collection
![](/assets/login uml.PNG)

Key class
![](/assets/keys uml.PNG)

### **Evolution of the key class**
We started with static keys, but this gave some issues.
After this we made a random generator for the keys.
We refactored the keys class and made some extra functions.
### **Problems**
The first problem that occured was when we made the keys dynamic.
The keys were not yet linked to a game so you could login with any random generated key.
The second problem was not a problem with the keys but more with the database, we had more and more database errors, you just had to refresh the page to fix it.
But we needed to lessen the workload of the database.
We did this by adding a bulkinsert function to the database class.
Instead of opening 4 connections to the database we needed only 2.
The third problem were just bad functions in the key class.
### **Fixes**
We fixed all of these problems by a lot of refactoring of the database and key class.
We also linked the keys to a game so that every key that was generated belonged only to 1 function (team or gamemaster)