# Adding REST Support

The main purpose of this version of Donation is to connect to a Web Service ([our sister site](http://donationweb-4-0.herokuapp.com)) and be able to retrieve, insert and delete Donations.

To make things a bit easier I've devloped a simple API to make the HTTP calls and convert the responses from JSON into objects our Android App can use.

So go ahead and download the package [here](../archives/api.zip).

The extracted archive consists of the following:

* DonationApi.java
* Rest.java


![](../img/lab6s201.png)

You will need to add these classes to your Android Studio Project and the simplest way is to copy the api folder in Windows Explorer or Finder and paste directly into your <b>ie.app</b> package in your Android Studio Project. Once completed, your project should look something like this:

![](../img/lab6s202.png)

Now, you'll have a number of errors, so first thing to do is add <b> Googles Gson's</b> dependency to our project
