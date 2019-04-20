# Splash screen for android using kotlin

Just follow the step bellow:

## 01. Create a new layout named "activity_splashscreen.xml"

## 02. Create your own theme named "SplashTheme" in "styles.xml"
```xml
<!-- Custom application theme. -->
<style name="SplashTheme" parent="Theme.AppCompat.Light.NoActionBar">
</style>
```

## 03. Change the "AndroidManifest.xml" file
```xml
<application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
    <activity android:name=".SplashscreenActivity" android:theme="@style/SplashTheme" android:noHistory="true">
        <intent-filter>
            <action android:name="android.intent.action.MAIN"/>

            <category android:name="android.intent.category.LAUNCHER"/>
        </intent-filter>
    </activity>
    <activity android:name=".MainActivity">
    </activity>
</application>
```

## 04. Create a new activity named "SplashscreenActivity"
```kotlin
// override the "Thread Object"
val background = object: Thread() {
	override fun run() {
		try {
		    // add sleep for 5 sec
			Thread.sleep(5000)
			
			// add destination activity
			val intent = Intent(baseContext, MainActivity::class.java)
			startActivity(intent)
		} catch(e: Exception) {
			e.printStackTrace()
		}
	}
}

// call the object
background.start()
```

Thanks