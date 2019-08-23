# KontactPicker
[![](https://jitpack.io/v/deepakkumardk/KontactPicker.svg)](https://jitpack.io/#deepakkumardk/KontactPicker)

A ContactPicker library for Android, written in [Kotlin](http://kotlinlang.org)

## Usages
project/build.gradle
```groovy
allprojects {
	repositories {
	    maven { url 'https://jitpack.io' }
	}
}
```

app/build.gradle
```groovy
dependencies {
        implementation 'com.github.deepakkumardk:KontactPicker:$latest-version'
}
```

### Activity

**NOTE: This library is based on AndroidX artifacts**

No need to specify the **READ_CONTACT** permission in your manifest file, library will handle this permission internally

```kotlin
    KontactPicker.Builder(this)
            .showPickerForResult(3000) //REQUEST_CODE
```

### Customization
```kotlin
    KontactPicker.Builder(this)
            .setDebugMode(true)
            .setImageMode(ImageMode.TextMode)       //Default is None
            .setSelectionTickView(SelectionTickView.LargeView)      //Default is SmallView
            .showPickerForResult(3000) //REQUEST_CODE
```

#### Handing Results
```kotlin
    override fun onActivityResult(requestCode: Int, resultCode: Int, data: Intent?) {
        super.onActivityResult(requestCode, resultCode, data)
        if (resultCode == Activity.RESULT_OK && requestCode == 3000) {
            val list = KontactPicker.getSelectedKontacts(data)  //ArrayList<MyContacts>
            //Handle this list
        }
    }
```


## License

```
 Copyright 2019 Deepak Kumar

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
   ```
