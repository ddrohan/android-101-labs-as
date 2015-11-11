# Activity Donate - Get Total Donated (so far)

When our Donation App initially starts we want to ensure that the current total (if any) is set correctly and corresponds to the donations listed on our sister web app.

We need to retrieve a list of all our donations from the Server and set our total. We will achieve this through our REST classes and the use of AsyncTasks to execute those calls on a background thread.

Before we start, we need to allow our app to access the internet (and network) so we need to add some permissions to our manifest file, so add the following to your <b>AndroidManifest.xml</b> file (just before the <application tag)  

~~~xml
    <uses-permission android:name="android.permission.INTERNET"/>
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
~~~

