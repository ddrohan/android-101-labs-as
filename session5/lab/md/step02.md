#Adding a new Menu Option

First of all, confirm that the current Menu looks like this:

![](../img/lab5s201.png)

but we want something like this:

![](../img/lab5s202.png)

The first thing to do is add in a new resource in strings.xml (or use Android Studio (Alt + Return) to fix the string resource error if you paste in the menu item directly)

~~~xml
 	<string name="menuReset">Reset</string>
~~~

and then the corresponding menu item in donate.xml

~~~xml
 	<item
        android:id="@+id/menuReset"
        android:orderInCategory="100"
        android:showAsAction="never"
        android:title="@string/menuReset"
        android:onClick="reset"/> 
~~~

It's probably worth removing the 'Settings' menu item at this stage too, and its related method in the Base class. Next, edit <b>Base.java</b> and add in the following method stub

~~~java
public void reset(MenuItem item) {}
~~~

to ensure our app won't crash when the menu loads (and looks for a method 'reset')

Run the app again and confirm you get the following Menu :

![](../img/lab5s202.png)

We can't implement this menu option fully yet, so for the moment, we'll just 'reset' the target amount back to zero (0) - Step 03.

