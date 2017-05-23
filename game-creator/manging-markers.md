# Managing Markers

Manage Google map markers, has been a hard work and difficult. We have had various problems, which we have been resolving throughout the project. We will now make a summary of how evolved, and the final result that we have achieved.

First we create a button to manually enter the longitude and latitude.  When we wrote a coordinate,  a marker appeared on the map in the corresponding point.

![](/assets/LocationAndLongitude.png)

It worked, and we wanted to go further. We thought that it would be easier for the user to click on the screen to select the point that the user knew exactly the coordinate \(latitude and longitude\) of the point that he wanted to add. So, we decided when the user click with the right button at one point specific to the map, a marker will appear at the point of the map that was clicked.![](/assets/mapMarker1.png)

When we already knew how to correctly add the marker, we think on how to add some kind of information about the mission we wanted to create. We think that the best thing would be that when we clicked with the right mouse button, a pop-up window is opened and all the relevant information had to fill in. This information is:

* Mission Number: it is set automatically by the program.
* Name Mission: Official name of the mission.
* Objectuve: Objective of the mission.
* Position: Latitude and longitude. We obtain this value when we click on the map. The position is variable.
* Radius: The radius of the marker that you want in each mission.

Add the radio on the map was not an issue, because the library where we are based, had a specific method to add a circle to the map.

![](/assets/AddDialogWindow.png)































