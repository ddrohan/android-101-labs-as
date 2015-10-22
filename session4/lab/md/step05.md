#Refactored Menu - New 'Event Handling'

If you recall from Step 01, our Base class has 3 particular methods that we haven't made use of - yet

~~~java
  public void settings(MenuItem item)
  {
    Toast.makeText(this, "Settings Selected", Toast.LENGTH_SHORT).show();
  }
  
  public void report(MenuItem item)
  {
    startActivity (new Intent(this, Report.class));
  }
  
  public void donate(MenuItem item)
  {
    startActivity (new Intent(this, Donate.class));
  }
}

~~~

We will now use these methods, and using the <b>onClick</b> attribute in our MenuItems, we will 'bind' these methods to our menu options.

Firstly, edit your menu_donate.xml and ensure it now looks as follows: 

~~~xml
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools" tools:context=".Donate">

    <item android:id="@+id/action_settings"
        android:title="@string/action_settings"
        android:orderInCategory="100"
        app:showAsAction="never"
        android:onClick="settings"/>

    <item
        android:id="@+id/menuReport"
        android:orderInCategory="100"
        android:title="@string/menuReport"
        app:showAsAction="never"
        android:onClick="report"/>

    <item
        android:id="@+id/menuDonate"
        android:orderInCategory="100"
        android:title="@string/menuDonate"
        app:showAsAction="never"
        android:onClick="donate"/>
</menu>
~~~

<b>note the added onClick attributes for each MenuItem, it directly corresponds to the method names in our Base class </b>


We can now refactor our Donate & Report classes and <b>Remove</b> the menu inflation and event handling code in both classes.

So, both classes should look as follows:

<b>Donate.java</b>
~~~java

~~~

<b>Report.java</b>
~~~java

~~~

Run your app once more, to confirm the changes and that your menu still works as it should.

