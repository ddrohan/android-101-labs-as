# Activity Donate - Get Total Donated (so far)

When our Donation App initially starts we want to ensure that the current total (if any) is set correctly and corresponds to the donations listed on our sister web app.

We need to retrieve a list of all our donations from the Server and set our total. We will achieve this through our REST classes and the use of AsyncTasks to execute those calls on a background thread.

Before we start, we need to allow our app to access the internet (and network) so we need to add some permissions to our manifest file, so add the following to your <b>AndroidManifest.xml</b> file (just before the <application tag)  

~~~xml
    <uses-permission android:name="android.permission.INTERNET"/>
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
~~~

Introduce the following <b>private</b> class into the Donate activity

~~~java
private class GetAllTask extends AsyncTask<String, Void, List<Donation>> {

        protected ProgressDialog 		dialog;
        protected Context 				context;

        public GetAllTask(Context context)
        {
            this.context = context;
        }

        @Override
        protected void onPreExecute() {
            super.onPreExecute();
            this.dialog = new ProgressDialog(context, 1);
            this.dialog.setMessage("Retrieving Donations List");
            this.dialog.show();
        }

        @Override
        protected List<Donation> doInBackground(String... params) {
            try {
                Log.v("donate", "Donation App Getting All Donations");
                return (List<Donation>) DonationApi.getAll((String) params[0]);
            }
            catch (Exception e) {
                Log.v("donate", "ERROR : " + e);
                e.printStackTrace();
            }
            return null;
        }

        @Override
        protected void onPostExecute(List<Donation> result) {
            super.onPostExecute(result);
            
            //use result to calculate the totalDonated amount here

            progressBar.setProgress(app.totalDonated);
            amountTotal.setText("$" + app.totalDonated);

            if (dialog.isShowing())
                dialog.dismiss();
        }
    }
~~~

To actually invoke this Task, add the following method 

~~~java
@Override
    public void onResume() {
        super.onResume();
        new GetAllTask(this).execute("/donations");
    }
~~~

Once 