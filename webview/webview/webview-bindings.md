# WebView bindings

Did you know that in an Android app with a WebView it is not only possible to invoke a Java method from JavaScript, but also to invoke JavaScript from the Java code?

VIDEO

### Invoke Java methods from JavaScript

To invoke a Java method from JavaScript in three steps first \(1\) create a new class with at least one method annotated with `@JavaScriptInterface`. Annotated methods will be made available from JavaScript.

```text
public class WebAppInterface {
    private Context mContext;
    WebAppInterface(Context context) {
        mContext = context;
    }

    @JavascriptInterface
    public void showToast(String toast) {
        // In this method you can do anything you want
        Toast.makeText(mContext, toast, Toast.LENGTH_SHORT).show();
    }
}
```

{% hint style="info" %}
Note that to show a toast you need access to the context which is why the variable mContext and the constructor is needed.
{% endhint %}

Then second \(2\) on the WebView instance invoke the method addJavascriptInterface. As the first argument create a new instance of the class previously created and as the second argument provide a string to be used as the name of the interface from JavaScript.

```text
myWebView.addJavascriptInterface(new WebAppInterface(this), "Android")
```

Now in the interface `Android` is available from the JavaScript code that runs in the WebView and annotated methods can be invoked directly. Third \(3\) in JavaScript invoke the provided Java methods.

```text
function showAndroidToast(toast) {
    Android.showToast(toast);
}

showAndroidToast("Hello from JavaScript running in WebView!");
```

{% hint style="info" %}
[Building web apps in WebView](https://developer.android.com/guide/webapps/webview#UsingJavaScript%20)
{% endhint %}

### Invoke JavaScript from Java

To invoke JavaScript from Java in two steps first \(1\) create a JavaScript method, e.g.  `showMessage()`.

```text
function showMessage(message) {
    var span = document.getElementById('message')
    span.innerText = message;
    setTimeout(function() { span.innerText = ''; }, 5000);
}
```

JavaScript can then be evaluated by \(2\) invoking the `WebView` instance method `evaluateJavascript` with the JavaScript to execute as the first argument and null as the second argument.

```text
myWebView.evaluateJavascript("showMessage('Hello from Java in Android!');", null);
```

{% hint style="info" %}
Please note that the evaluated JavaScript might fail, e.g. if the function `showMessage` is not defined.
{% endhint %}

