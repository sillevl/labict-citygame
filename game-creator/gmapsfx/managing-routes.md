
#**Routes**
![](/assets/route1.png)

## **How does it work?**

For routes to work you need atleast 2 markers/missions.
When you have 2 missions or more you can click the Create paths button which will create a route between the 2 missions. If there are more missions the path will go from mission 1 to mission 2 to mission 3 and so on.

### Code
the 1st and 2nd if operator are used to check if the fromID and toID match the missionID, If they match the latitude and longitude will be stored as strings into a LatLong object (called Van and Naar). Also the latitude and longitude will be stored individually into a double.

The 3rd if operator is used to check if Van and Naar aren't null and that they don't equal each other, because there are cases where one can be null or they match each other and then you will end up with awkward results. If the condition is matched a new direction service will be started which eventually will end up drawing the path between two locations 

The for loop is used to go through all missions. At the end of the for loop a 1 will be added to fromID and toID so when the next time you go through the for loop it will go from mission 2 to mission 3 and so on.

```cpp


       
               int fromID = 1;
               int toID = 2;
               
             for (int i = 0; i < auxiliarGtlg.getMissionNumber() ; i++) {
                if (fromID ==auxiliarGtlg.getMissionNumber()) {
                Van = (Double.toString(auxiliarGtlg.getLocations().get(0).getLatitude()) + ", " + Double.toString(auxiliarGtlg.getLocations().get(0).getLongitude()));         
                fromLat = auxiliarGtlg.getLocations().get(0).getLatitude();
                fromLong = auxiliarGtlg.getLocations().get(0).getLongitude();

                }
            
               if (toID ==auxiliarGtlg.getMissionNumber()){
                 Naar = (Double.toString(auxiliarGtlg.getLocations().get(0).getLatitude()) + ", " + Double.toString(auxiliarGtlg.getLocations().get(0).getLongitude()));
                toLat = auxiliarGtlg.getLocations().get(0).getLatitude();
                toLong = auxiliarGtlg.getLocations().get(0).getLongitude();               
               }

                if (Van!=null && Naar!=null && !Van.equals(Naar) && !Naar.equals(Van)){
                DirectionsService ds = new DirectionsService();
                DirectionsRequest request = new DirectionsRequest(Van,Naar, TravelModes.WALKING);            
                ds.getRoute(request, this, renderer);   


              }
                fromID++;
                toID++;
  }
```

## **What else does routes has to offer.**

When routes have been made it is possible to calculate the distance and time in bird eye's view. This is the fastest possible way to go from 1 location to a second one.

![](/assets/distancetime.png)

### code
**Note:** The code is part of the previous for loop.

It uses the latitude and longitude doubles which (from the code above) and uses them in a formula to calculate the distance which eventually will be stored in a double called totalD and it will do that for all the paths that are made and eventually when all that is done the total distance will be set into label in topbar.

                double dLat = (toLat - fromLat) * Math.PI / 180;
                double dLon = (toLong - fromLong) * Math.PI / 180;

                double a = Math.sin(dLat / 2) * Math.sin(dLat / 2)
                        + Math.cos(fromLat * Math.PI / 180)
                        * Math.cos(toLat * Math.PI / 180)
                        * Math.sin(dLon / 2) * Math.sin(dLon / 2);
                

                double c = 2.0 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a));
                double d = EarthRadiusMeters * c;
                totalD += d;
  
                System.err.println("Distance is: " + totalD +"Meters");   

When the distance is calculated you can also calculate the time with a simple math formula and when thats done it will also be printed out into a label in the topbar.

![](/assets/route2.png)

One more example of routes with multiple missions.