# Android Device Monitor

As an exercise of sorts, you should become familar with the Android Device Monitor, particularly how it relates to viewing your database on the emulator/device. 

![](../img/lab5s901.png)
---

In Android Studio, you launch the Android Device Monitor as follows:

Tools->Android->Android Device Monitor (as below)

![](../img/lab5s902.png)

Next, you need to navigate to the data/data folder within the application package on the device (in our case ie.app) like so:

![](../img/lab5s903.png)

Then, scroll/find your database (donations.db) in the ie.app.databases folder:

![](../img/lab5s904.png)

Select the "Pull a file from the Device" on the top right-hand-side of the window:

![](../img/lab5s905.png)

and save your database file to a local folder.

Next download and install [sqlitebrowser](http://sqlitebrowser.org) which will allow us to view our database graphically.

![](../img/lab5s906.png)

Launch your sqlitebrowser app/program to get this window:

![](../img/lab5s907.png)

and then 'Open Database' selecting the database you pulled from the device. If everything goes to plan, you should be able to view your database table(s) and their content, as well as the SQL that created the tables.

Below, we can see a donations table with 3 donations

![](../img/lab5s908.png)

and the corresponding entries in our Android App.

![](../img/lab5s909.png)

