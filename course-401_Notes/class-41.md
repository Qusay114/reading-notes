# Intent Filters : 

Allowing Other Apps to Start Your Activity و To allow other apps to start your activity , you need to add an <intent-filter> element in your manifest file for the corresponding <activity> element.

When your app is installed on a device, the system identifies your intent filters and adds the information to an internal catalog of intents supported by all installed apps. When an app calls startActivity() or startActivityForResult(), with an implicit intent, the system finds which activity (or activities) can respond to the intent.

### Add an Intent Filter :

In order to properly define which intents your activity can handle, each intent filter you add should be as specific as possible in terms of the type of action and data the activity accepts.

The system may send a given Intent to an activity if that activity has an intent filter fulfills the following criteria of the Intent object:

* Action :
A string naming the action to perform. Usually one of the platform-defined values such as ACTION_SEND or ACTION_VIEW.

* Data :
A description of the data associated with the intent.Specify this in your intent filter with the <data> element.

* Category :
Provides an additional way to characterize the activity handling the intent, usually related to the user gesture or location from which it's started. There are several different categories supported by the system, but most are rarely used. However, all implicit intents are defined with CATEGORY_DEFAULT by default.

Example : 

        <activity android:name="ShareActivity">
            <intent-filter>
                <action android:name="android.intent.action.SEND"/>
                <category android:name="android.intent.category.DEFAULT"/>
                <data android:mimeType="text/plain"/>
                <data android:mimeType="image/*"/>
            </intent-filter>
        </activity>


### Handle the Intent in Your Activity :

In order to decide what action to take in your activity, you can read the Intent that was used to start it.

As your activity starts, call getIntent() to retrieve the Intent that started the activity. You can do so at any time during the lifecycle of the activity, but you should generally do so during early callbacks such as onCreate() or onStart() .

Example : 

        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);

            setContentView(R.layout.main);

            // Get the intent that started this activity
            Intent intent = getIntent();
            Uri data = intent.getData();

            // Figure out what to do based on the intent type
            if (intent.getType().indexOf("image/") != -1) {
                // Handle intents with image data ...
            } else if (intent.getType().equals("text/plain")) {
                // Handle intents with text ...
            }
        }


### Return a Result : 

If you want to return a result to the activity that invoked yours, simply call setResult() to specify the result code and result Intent. When your operation is done and the user should return to the original activity, call finish() to close (and destroy) your activity.

Example :

        // Create intent to deliver some kind of result data
        Intent result = new Intent("com.example.RESULT_ACTION", Uri.parse("content://result_uri"));
        setResult(Activity.RESULT_OK, result);
        finish();

<br><br><br>
![image1](https://tutorial.eyehunts.com//wp-content/uploads/2018/06/what-is-android-Intent-Filters-examples.png)
