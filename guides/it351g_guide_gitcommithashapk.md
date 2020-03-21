# Add git hash to APK file name

To match the APK files uploaded as part of the assignments with a given snapshot \(commit\) of the git repository we require the APK file name to include the git commit hash of the latest commit. To add the git commit hash to the APK file name add a `applicationVariants.all` block in the android block in `app\build.gradle`

```text
apply plugin: 'com.android.application'

android {
    compileSdkVersion 28
    ...

    applicationVariants.all { variant ->
        variant.outputs.all {
            outputFileName = "${rootProject.name}-${variant.name}-" + {
                def stdout = new ByteArrayOutputStream()
                exec {
                    commandLine 'git', 'describe', '--match=', '--always', '--dirty'
                    standardOutput = stdout
                }
                stdout.toString().trim()
            }() + ".apk"
        }
    }
}

dependencies {
    ...
}
```

