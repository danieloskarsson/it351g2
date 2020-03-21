# Activities

In mobile application the area seen on the mobile device is often referred to as a **screen**. The term screen is _not_ Android-specific, same term is used by designers when creating prototypes and by developers of other platforms to refer to the content in the screen rather than the technical artifact behind it. Examples of screens are: the login screen, the preferences screen, the list of mountains, and the mountain details screen. On the web developers usually use the term **page** to describe these. In Android the technical artifact behind a screen is called an `Activity`. Activities provide a surface in which Views, Layouts, and Fragments are drawn.

All Android apps must contain at least one Activity which is started when the user taps the app icon on the home _screen_. An activity consist of two parts: A class, e.g. `MainActivity` and a layout, e.g. `activity_main`. The layout is a XML file in which Layouts and Views are declared, e.g. a button. The class is a Java file in which Java code is used to program the behavior of the screen, e.g. what should happen when the user taps a button. All activities must be added the application manifest or the app will crash when used. New activities can be added in Android Studio via the menu `File > New > Activity > Empty Activity`, which adds the activity to the manifest automatically.

VIDEO

Activities are bound by something called the Activity Lifecycle that determines what the Activity should do depending on the state of the application. The Activity Lifecycle will not be discussed in details and no questions will be asked about it during the home exam. The two methods that are used the most is the `onCreate()` method which is called when the activity is created and the `onResume()` method that is called when the user returns to the activity. Examples of when the user returns to the activity is when a second activity was opened on top of the first activity and the second activity is then closed by the user, or when the user has switched to another app and is switching back to your app.

{% hint style="info" %}
**Further reading:** [Introduction to Activities](https://developer.android.com/guide/components/activities/intro-activities)
{% endhint %}

