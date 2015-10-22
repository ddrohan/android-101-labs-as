#Menu Revisited

When you navigate from the Donate activity to reports, there will be no menu available. So we need to first inflate the menu like so

~~~java
@Override
    public boolean onCreateOptionsMenu(Menu menu) {
        // Inflate the menu; this adds items to the action bar if it is present.
        getMenuInflater().inflate(R.menu.menu_donate, menu);
        return true;
    }
~~~

Bring in a new menu item, 'Donate' - Donate should bring you back to the main Donate Screen.

This is a very similar approach to what you did in Step 02, so revisit this step and see if you can end up with something like the following for the 'Report' Screen:

![](../img/lab3s401.png)

We'll look at populating the list with actual donations in the next lab.