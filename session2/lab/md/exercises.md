#Exercises

Archive of lab so far:

- [Donation.1.0.zip](../archives/Donation.1.0.zip)

##Exercise 1:

Consider an alternative to the NumberPicker - specifically one of the "Text Fields" controls:

These are mostly EditView objects:

- <http://developer.android.com/reference/android/widget/EditText.html>

Redesign the activity to take a value from the picker or directly from a text view and maintain a "Total so Far" Value:

![](../img/lab2s902.png)

![](../img/lab2s901.png)

![](../img/lab2s903.png)

If the number picker is set to zero, then attempt to get a number from the text view.

Here is a hint (a version of donatButonPressed that does what we want):

~~~java
  public void donateButtonPressed (View view) 
  {
    String method = paymentMethod.getCheckedRadioButtonId() == R.id.PayPal ? "PayPal" : "Direct";
    progressBar.setProgress(totalDonated);

    int donatedAmount =  amountPicker.getValue();
    if (donatedAmount == 0)
    {
      String text = amountText.getText().toString();
      if (!text.equals(""))
        donatedAmount = Integer.parseInt(text);
    }
    totalDonated  = totalDonated + donatedAmount;
    Log.v("Donate", amountPicker.getValue() + " donated by " +  method + "\nCurrent total " + totalDonated);
   }
~~~

##Exercise 2:

Revise the app such that when the target is achieved (10000) - then no more donations accepted, and the user is made aware of this.

Hint - here is how you can display a simple alert:

~~~java
      Toast toast = Toast.makeText(this, "Target Exceeded!", Toast.LENGTH_SHORT);
      toast.show();
~~~

##Exercise 3:

Modify the colour scheme for our widgets..

You will notice that the Floating Action Button, the Radio Buttons, the Progress Bar etc, are all a kind of pink - not really in line with our current colour scheme.

Hint - have a look at your <b>colors.xml</b> 


![](../img/lab2s904.png)


Archive of lab with the above Exercises:

- [Donation.1.5.zip](../archives/Donation.1.5.zip)

