# HTTP networking

HTTP networking is surprisingly complex. The first step is to allow the app to read the network state and to connect to the internet by adding the permissions in the application manifest `AndroidManifest.xml`.

```text
<manifest xmlns:android="...">
    
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <uses-permission android:name="android.permission.INTERNET" />

    <application ...
```

 Second there is a choice of which HTTP client to use. In this course the only client that will be discussed is the `HttpsURLConnection` client which is provided by the Android plattform.

One of the factors that make HTTP networking is that it takes between data is requested and it being received. Due to this, networking has to be performed separate from the part of the app  that manages the user interface. The network operation and the UI is executed in different threads.

...

{% hint style="info" %}
**Further reading:** [Use HTTPSUrlConnection to fetch data](https://developer.android.com/training/basics/network-ops/connecting#download)
{% endhint %}

