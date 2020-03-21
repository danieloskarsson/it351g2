# Intents

To start a new Activity we use an Intent. Intents are messaging objects which means that they can also be used to pass data from one Activity to another. Intents also have other uses such as starting different types of app components including components from other applications, e.g. composing a new email. In this course intents will only be used to start a new Activity in the same app. In the example below an intent is created, the name Daniel and number 1 is attached and the intent is used to start `SecondActivity`.

```text
Intent intent = new Intent(MainActivity.this, SecondActivity.class);
intent.putExtra("name", "Daniel"); // Optional
intent.putExtra("number", 1); // Optional
startActivity(intent);
```

{% hint style="warning" %}
Notice the difference between `MainActivity.`**`this`** and `SecondActivity.`**`class`**. The use of the keyword `this` is because that we already have a MainActivity while the keyword `class` is used to denote an uninstantiated SecondActivity. Don't worry if you don't understand the difference in full, we will ask no questions regarding this during the exam.
{% endhint %}

Normally no action is needed to handle the intent in the `SecondActivity`. However, if there are attached data as the case name and number above, that data is made available from the intent in the form of a `Bundle`.

```text
Bundle extras = getIntent().getExtras();
if (extras != null) {
    String name = extras.getString("name");
    int number = extras.getInt("number");
    // Do something with the name and number
}
```

{% hint style="danger" %}
Note that the bundle may not exists, e.g. if no data was attached, so it is important to check if the bundle if null before it is being accessed, or the application might crash.
{% endhint %}

VIDEO

{% hint style="info" %}
**Further reading:** [Intents and Intent filters](https://developer.android.com/guide/components/intents-filters)
{% endhint %}

