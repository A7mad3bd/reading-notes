# Intent Filters

## Read 38

## What is an Intent?

- An intent is a messaging object you can use to request an action from another app component.

##  Allowing Other Apps to Start Your Activity

- If your app can perform an action that might be useful from another app, your app should be prepared to respond to action requests by specifying the appropriate intent filter in your activity.
- For example, if you build a social app that can share messages or photos with the user's friends, you should support the ACTION_SEND intent


### Starting an activity

- An activity represents a single screen in an app. The intent describes the activity to start and carries any necessary data.


## Intent types
### There are two types of intents:

 - Explicit intents specify which application will satisfy the intent, by supplying either the target app's package name or a fully-qualified component class name. You'll typically use an explicit intent to start a component in your own app, because you know the class name of the activity or service you want to start. 

For example, you might start a new activity within your app in response to a user action, or start a service to download a file in the background.

- Implicit intents do not name a specific component, but instead declare a general action to perform, which allows a component from another app to handle it. For example, if you want to show the user a location on a map, you can use an implicit intent to request that another capable app show a specified location on a map.

### Intent filters

- An intent filter is an expression in an apps manifest that specifies the type of intents that the componenet would lkke to recieve.
- For instance, by declaring an intent filter for an activity, you make it possible for other apps to directly start your activity with a certain kind of intent. 


### Add an Intent
- In order to allow other apps to use your activities you need to add an intent filter element to the manifest portion for that activity.
- For example you need to send a photo, your app will show up as an option to send the photo.
- When the app is intstalled, your device will find intents that can respond to the intent'
- `<action>` element to specify the action in the intent filter
- `<data>` specify MIME type, just a URI prefix, just a URI scheme, or a combination of these and others that indicate the data type accepted
- `<category>` this usually related to users gestures or location
- example:
````XML
    <activity android:name="ShareActivity">
    <intent-filter>
        <action android:name="android.intent.action.SEND"/>
        <category android:name="android.intent.category.DEFAULT"/>
        <data android:mimeType="text/plain"/>
        <data android:mimeType="image/*"/>
    </intent-filter>
</activity>
````


#### Handle the Intent in Your Activity

- Figuring out what intent to use for the activity example
````Java
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
````


## Resources

- [Intent Filters](https://developer.android.com/guide/components/intents-filters)
- [Implicit vs. Explicit Intents](https://developer.android.com/training/basics/intents/filters)

