# Fragments

Fragments was first introduced in Android 3 and was initially targeted at Android devices with a larger physical screen, e.g. to keep a list of mountains to the left of a mountain details screen instead of putting the mountain details screen on top of the list of mountains.

However, fragments also has a prominent role in apps that run on smaller devices. Fragments can be used for a variety of tasks such as providing different layouts based on different parameters such as the screen size or screen orientation. Fragments is also used to represent tabs and may even cover 100% of its parent activity surface, e.g. to implement an onboarding screen \(the type of screen that some apps show the first time ever an app is launched to tell you about its features\).

As with Activities, Fragments consist of  a class, e.g. `FragmentOne` and a layout, e.g.`fragment_one`. Also as with Activities, Fragments are also bound to a lifecycle called the Fragment Lifecycle. The Fragment Lifecycle is similar but is different than the Activity Lifecycle, the Fragment Lifecycle also include the `onCreate()` and `onResume()` methods. As with the Activity Lifecycle no questions will be asked about the Fragment Lifecycle on the home exam.

Fragments are attached to the activity either by declaring it in the activity layout or by programmatically adding a fragment to an existing layout with the help of instances of `FragmentManager`and `FragmentTransaction`. Individual fragments should always declare a unique id and tag to allow them to be modified. Once added fragments can be added, removed, or replaced using `FragmentManager`and `FragmentTransaction`. 

{% hint style="info" %}
**Further reading:** [Fragments](https://developer.android.com/guide/components/fragments)
{% endhint %}

