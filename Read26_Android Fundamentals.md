# Android Fundamentals


## Basics 


- Android apps can be written using Kotlin, Java, and C++ languages.
- An android package which is an archive file with an `.apk` suffix contains the contents of an android app that are required at runtime and it is the file that android powered devices use to install the app.
- The android system implements the principle of least privilege. That is each app by default has access only to the components that it required to do its work and no more.


## What are app components?


- An app component is the essential building block of an android app. 
- Each component is an entry point through which the system or a user can enter your app. 

## Four different types of app components

1. Activities
2. Services
3. Broadcast receivers
4. Content providers

## What is an activity?

- An activity is the entry point for intertacting with the user. It represents a single screen with a user interface. For example an email app might have one activity that shows a list of new emails, another activity to compose an email, and other for reading emails.

## What are services?

- A service is a general-purpose entry point for keeping an app running in the background for all kinds of purposes.
- Does not provide a user interface.
- For example, a service might play music in the background while the user is in a different app. 

## What is a broadcast receiver?

- A BR is a component that enables the system to deliver events to the app outside of a regular user flow. Allowing the app to respond to system-wide broadcast announcements. 

## What are Contents Providers?

- A CP manages a shared set of app data that you can store in the file system, in a database, on the web, or on any persistent storage location that your app can access.


## Manifest File


- Before the android system can start app components, the system must know that the component exists by reading the app's manifest file. `androidManifest.xml`
- Your app must declare all its components in this file, which must be at the root of the app project directory.

## Resources

- [Android fundamentals](https://developer.android.com/guide/components/fundamentals)