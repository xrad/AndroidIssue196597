# Demonstration for Android Issue 196597

https://code.google.com/p/android/issues/detail?id=196597

## Instructions

1. Compile in Android Studio

2. Execute the following instructions:

```shell
adb install app/build/outputs/apk/app-debug.apk
adb shell am start -S 'com.android.settings/.Settings\$DeviceAdminSettingsActivity'
```

You should be able to register/unregister the sample app as device administrator.

Now execute this to briefly allow/deny SYSTEM_ALERT_WINDOW.

```shell
adb shell appops set sample.androidissue196597 SYSTEM_ALERT_WINDOW allow
adb shell appops set sample.androidissue196597 SYSTEM_ALERT_WINDOW deny
adb shell am start -S 'com.android.settings/.Settings\$DeviceAdminSettingsActivity'
```

Now you will get a force-close of the system settings app.