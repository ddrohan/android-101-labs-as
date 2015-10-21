#Package Name

This is the current version of the <b>Donation</b> app:

- [Donation.1.5.zip](../archives/Donation.1.5.zip)

To continue using this project we need to 'refactor' it to <b>Donation.2.0</b>. At the time of writing, Android Studio's refactoring features and tools are a bit iffy :-) so we'll need to manually copy our project.

1. Ensure you don't have <b>Donation.1.5</b> open in Android Studio - if you do, close it now
2. navigate to the folder where you downloaded and unzipped <b>Donation.1.5</b>
2. Rename (or copy if you wish) the folder to <b>Donation.2.0</b>
3. rename the file <b>Donation.1.5.iml</b> to <b><i>Donation.2.0.iml</i></b>
4. Edit this file and change any references to <b>Donation.1.5</b> to <b>Donation.2.0</b>
5. navigate to the <b>.idea</b> folder (it might be a hidden folder) open the <b>.name</b> file and rename the project name to <b>Donation.2.0</b>
6. Launch Android Studio and open up the <b>Donation.2.0</b> project



~~~xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="app.donation"
    android:versionCode="1"
    android:versionName="1.0" >
~~~

Once you save this - it would regenerate the correct 'gen' files. Delete the old one as we no longer need it (com.example.donation)

We should also take this opportunity to change the name of the 'donation' package to 'app.activities'. Android does not like packages with a single 'segment'.


![](../img/02.png)