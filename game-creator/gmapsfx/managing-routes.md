![](/assets/distance&time.PNG)

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

When routes are have been made it is possible to calculate the distance and time in bird eye's view




