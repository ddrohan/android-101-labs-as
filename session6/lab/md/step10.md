# Donate Activity - Reset/Delete all Donations

The final step in this lab is the ability to delete, or reset, all our Donations.


## Remember - once you reset the Donations associated with this version of our Server (donationweb-4-0) Everyones Donations will be deleted, so you'll have to add in more Donations to keep testing your App.

Anyway :)

Let's finish off our Donation 5.0 App by implementing the 'Reset' Menu option. 

First thing to do is bring in this AsyncTask

~~~java
private class ResetTask extends AsyncTask<Object, Void, String> {

        protected ProgressDialog 		dialog;
        protected Context 				context;

        public ResetTask(Context context)
        {
            this.context = context;
        }

        @Override
        protected void onPreExecute() {
            super.onPreExecute();
            this.dialog = new ProgressDialog(context, 1);
            this.dialog.setMessage("Deleting Donations....");
            this.dialog.show();
        }

        @Override
        protected String doInBackground(Object... params) {

            String res = null;
            try {
                    res = DonationApi.deleteAll((String)params[0]);
            }

            catch(Exception e)
            {
                Log.v("donate"," RESET ERROR : " + e);
                e.printStackTrace();
            }
            return res;
        }

        @Override
        protected void onPostExecute(String result) {
            super.onPostExecute(result);

            app.totalDonated = 0;
            progressBar.setProgress(app.totalDonated);
            amountTotal.setText("$" + app.totalDonated);

            if (dialog.isShowing())
                dialog.dismiss();
        }
    }
~~~

There's really only one line of code which needs to be added to the reset() method so see if you can work out what it is and be able to 'reset' (delete) all the Donations on the Server.

If you get this all working, you'll notice there's a small bug in the app that allows the user to still view the Report Screen, even after we called the reset menu option.

See can you fix this bug and also add in a feature to ask the user if they're sure they want to reset all the donations (similar to the delete a Donation feature on the Report Screen).
