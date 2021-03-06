#Step 02 - Layout Donation Activity

For this lab, our objective is to produce an Android App that looks something like this:

![](../img/completeappv1.png)

In your <b>content_donate.xml</b>, delete the current 'Hello World' text, and drag and drop a new 'LargeText' form widget onto the canvas, and 'stretch' the widget to fill the canvas (like below). Look closely at the following:

![](../img/lab2s201.png)

Now, Double-Click the widget and you will be presented with the following:

![](../img/lab2s202.png)

Select the elipse (on the right hand side, indicated below)

![](../img/lab2s203.png)

and you will be presented with the Resources Menu

![](../img/lab2s204.png)

Select a 'New Resource->New String Value, and fill in the values as below

![](../img/lab2s205.png)

Double-Click the widget again and enter <b>donteTitle</b> for the <b>id</b> and hit return. 

![](../img/lab2s205a.png)

Once completed, you'll have something like this

![](../img/lab2s206.png)

Note carefully the following features:

- the guides tyeing the text to the left, top and right corner
- in Outline - the name of the control has been changed from a default to 'donateTitle'.
- in Properties - check the value for 'text' and notice we have a string reference linking to our <b>strings.xml</b> (below)

![](../img/lab2s207.png)

Locate the following two files and inspect them closely:

##res/layout/content_dontate.xml
~~~xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto" android:layout_width="match_parent"
    android:layout_height="match_parent" android:paddingLeft="@dimen/activity_horizontal_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    android:paddingBottom="@dimen/activity_vertical_margin"
    app:layout_behavior="@string/appbar_scrolling_view_behavior"
    tools:showIn="@layout/activity_donate" tools:context=".Donate">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceLarge"
        android:text="@string/donateTitle"
        android:id="@+id/donateTitle"
        android:layout_alignParentTop="true"
        android:layout_alignParentStart="true"
        android:layout_alignParentEnd="true" />
</RelativeLayout>
~~~

##res/values/strings.xml
~~~xml
<resources>
    <string name="app_name">Donation</string>
    <string name="action_settings">Settings</string>
    <string name="donateTitle">Welcome Homer</string>
</resources>

~~~

Note the relationship between 'donateTitle' in both files.

Bring in the following string into the donate activity now - (medium text) - and follow the same procedure as above. The designer should look like this:

![](../img/lab2s208.png)

and our XML files will look like this:

~~~xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto" android:layout_width="match_parent"
    android:layout_height="match_parent" android:paddingLeft="@dimen/activity_horizontal_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    android:paddingBottom="@dimen/activity_vertical_margin"
    app:layout_behavior="@string/appbar_scrolling_view_behavior"
    tools:showIn="@layout/activity_donate" tools:context=".Donate">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceLarge"
        android:text="@string/donateTitle"
        android:id="@+id/donateTitle"
        android:layout_alignParentTop="true"
        android:layout_alignParentStart="true"
        android:layout_alignParentEnd="true" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:text="@string/donateSubtitle"
        android:id="@+id/donateSubtitle"
        android:layout_below="@+id/donateTitle"
        android:layout_alignParentStart="true"
        android:layout_marginTop="27dp"
        android:layout_alignEnd="@+id/donateTitle" />
</RelativeLayout>
~~~
Our 'strings.xml' file....
~~~xml
<resources>
    <string name="app_name">Donation.1.0</string>
    <string name="action_settings">Settings</string>
    <string name="donateTitle">Welcome Homer</string>
    <string name="donateSubtitle">Please Give Generously</string>
</resources>
~~~



