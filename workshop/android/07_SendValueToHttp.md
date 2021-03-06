# Send value to HTTP API

To send data through `HTTP POST` you need [Internet access permission](http://developer.android.com/training/basics/network-ops/connecting.html).

1. Open `AndroidManifest.xml`
1. Add

`<uses-permission android:name="android.permission.INTERNET"/>`

in `manifest`node.

We recommend to use [OkHttp](http://square.github.io/okhttp/) has a HTTP client.

Add **OKHttp** dependency to `app/build.gradle`.

On Android network calls cannot be done on main thread.

Use a new [Thread](http://developer.android.com/reference/java/lang/Thread.html) to do stuff in another thread.

> Note: Using thread is prohibited in Android, instead, [Service](http://developer.android.com/guide/components/services.html) or [AsyncTask](http://developer.android.com/reference/android/os/AsyncTask.html) should be used. For demonstration purpose Thread fits our needs.


> Kotlin Tips
>
> Use [string interpolation](https://kotlinlang.org/docs/reference/idioms.html#string-interpolation) to easily generate JSON.

**POST** sensor **value**, **type**, **eventTime** and **smartphoneId** to `http://private-anon-772e55d6a-mnantern.apiary-mock.com/data` every *2 seconds*.

You can view the result of your request on [apiary](http://docs.mnantern.apiary.io/traffic).

Example:

`
  [{
    "smartphoneId": "blacroix",
    "type": "BRIGHTNESS",
    "eventTime": "2016-02-12T17:31:38Z",
    "value": "37"
  }]
`

> Kotlin Tips
>
> Use [companion object](https://kotlinlang.org/docs/reference/object-declarations.html#companion-objects) to set APIary as constant.

To be able to delay an action you can use [Handler](http://developer.android.com/reference/android/os/Handler.html).

Well done! You finished level 1 of workshop :horse:

You can now:

1. [Continue Kotlin with Springboot](../back/01_CreateProject.md)
2. [Enhance current Android application](08_ExtraAndroidApplication.md)
