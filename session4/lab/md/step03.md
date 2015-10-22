#Refactored Report - New 'Layout'

We now rework Report to render the actual donations - held in the Base class list.

First some layout additions. Include these new string resources in strings.xml

~~~xml
    <string name="defaultAmount">00</string>
    <string name="defaultMethod">N/A</string>
~~~

This is a new layout - to be called 'row_donate.xml'. Place this in the 'layout' folder.

~~~xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical" android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/row_amount"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentLeft="true"
        android:layout_alignParentTop="true"
        android:layout_marginLeft="48dp"
        android:layout_marginTop="20dp"
        android:text="@string/defaultAmount" />

    <TextView
        android:id="@+id/row_method"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="106dp"
        android:text="@string/defaultMethod"
        android:layout_alignTop="@+id/row_amount"
        android:layout_centerHorizontal="true" />

</RelativeLayout>
~~~

