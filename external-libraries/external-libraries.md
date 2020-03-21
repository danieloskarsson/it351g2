# External libraries

Using external libraries is a great way to take advantage of great work already provided by others. If there is an external library that already provide the functionality that you are looking to implement it _may_ be advantageous to include that external library as a dependency in your source code instead of creating your own implementation.

It should however be noted that including external libraries created by a third party is also a risk. The external library may be buggy, itself require the use of other libraries that you do not want to use, or the library may do mischievous things such as uploading user data to their own servers. As an app developer you are responsible for the application towards your customers despite the fact that you have not written all the functionality yourself.

This aside most well known external libraries provide good functionality of high quality in a light package. Using such libraries is usually a good idea because you can focus on developing the thing that makes your application unique.

In Android external libraries are added as a dependency in the projects `app\build.gradle` file.

```groovy
apply plugin: 'com.android.application'

android {
    compileSdkVersion 28
    buildToolsVersion "29.0.3"
    ...
}

dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation 'androidx.appcompat:appcompat:1.1.0'
    implementation 'com.android.support.constraint:constraint-layout:1.1.3'
    implementation 'com.google.android.material:material:1.2.0-alpha05'
    testImplementation 'junit:junit:4.12'
    androidTestImplementation 'androidx.test:runner:1.2.0'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.2.0'
}
```

{% hint style="info" %}
The dependencies in your project may be different depending on which version of Android Studio that was used to create the project.
{% endhint %}

To add a new dependency add a new line in dependencies and synchronize the project. The external library will automatically be downloaded from the internet and when the project has finished synchronizing you can use the library in your source code as described by the documentation of the external library. In the example below the external library [Picasso](https://square.github.io/picasso/) has been added to the projects `app/build.gradle` file.

```groovy
...

dependencies {
    implementation 'com.squareup.picasso:picasso:2.71828'
    ...
}
```

Which libraries can you find? Use a search engine to do some research and try out different libraries.

