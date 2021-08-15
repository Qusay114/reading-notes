# Application Fundamentals : 

Android apps can be written using Kotlin, Java, and C++ languages. The Android SDK tools compile your code along with any data and resource files into an APK or an Android App Bundle.The Android app contents is in an archive file with an .apk suffix , and this file is being used to install the application , while the android bundle , which is an archive file with an .aab suffix, contains the contents of an Android app project including some additional metadata that is not required at runtime, and is not installable on andoid devices .

Each Android app lives in its own security sandbox, protected by the following Android security features:

The Android operating system is a multi-user Linux system in which each app is a different user.
By default, the system assigns each app a unique Linux user ID (the ID is used only by the system and is unknown to the app). The system sets permissions for all the files in an app so that only the user ID assigned to that app can access them.
Each process has its own virtual machine (VM), so an app's code runs in isolation from other apps.
By default, every app runs in its own Linux process. The Android system starts the process when any of the app's components need to be executed, and then shuts down the process when it's no longer needed or when the system must recover memory for other apps.
Each app has access to his own components , and this called the principle of least privilege , However, there are ways for an app to share data with other apps and for an app to access system services:

It's possible to arrange for two apps to share the same Linux user ID, in which case they are able to access each other's files. To conserve system resources, apps with the same user ID can also arrange to run in the same Linux process and share the same VM. The apps must also be signed with the same certificate.

An app can request permission to access device data such as the device's location, camera, and Bluetooth connection. The user has to explicitly grant these permissions.


# App components :

There are four different types of app components:

1. Activities :
It's the entry point for interacting with the user , which represents a single screen with a user interface , it implements an activity as a subclass of the Activity .

2. Services : 

A service is a general-purpose entry point for keeping an app running in the background for all kinds of reasons ,it doesn't provides an user interface .

3. Broadcast receivers :

A broadcast receiver is a component that enables the system to deliver events to the app outside of a regular user flow, allowing the app to respond to system-wide broadcast announcements , broadcast receivers don't display a user interface  , A broadcast receiver is implemented as a subclass of BroadcastReceiver and each broadcast is delivered as an Intent object.

4. Content providers :

A content provider manages a shared set of app data that you can store in the file system, in a SQLite database, on the web, or on any other persistent storage location that your app can access , A content provider is implemented as a subclass of ContentProvider and must implement a standard set of APIs that enable other apps to perform transactions.

