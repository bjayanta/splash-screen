# Splash screen for android using kotlin
Just follow the step bellow:
01. 

## In main activity:
```kotlin
val background = object: Thread() {
	overeide fun run() {
		try {
			Thread.sleep(5000)
			
			val intent = Intent(baseContext, MainActivity::class.java)
			startActivity(intent)
		} catch(x: Exception) {
			e.printStackTrace()
		}
	}
}

backgrount.start()
```