# Booking

## Overview

![](/assets/booking.png)

Before a game can starting the users need to create a booking. This booking exist out of the general information of the group. When you want to pick a date you can only see the available dates. For this feature we use the jQuery datepicker Widget\*.

If a group select the "submit" button, than is the data going directly the collection booking of the database. To make this possible we're using our own booking class. When the data isn't valid the user gets an alert with the notification of what's wrong.

## UML Booking class

![](/assets/booking_class.png)

\*[https://jqueryui.com/datepicker/](https://jqueryui.com/datepicker/ "jQuery Datepicker")

