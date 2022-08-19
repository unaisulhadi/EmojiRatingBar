<h1 align="center">EmojiRatingBar</h1>

[![Kotlin Version](https://img.shields.io/badge/Kotlin-v1.7.10-blue.svg)](https://kotlinlang.org)  [![Platform](https://img.shields.io/badge/Platform-Android-green.svg?style=flat)](https://www.android.com/) [![API](https://img.shields.io/badge/API-21%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=21)
[![](https://jitpack.io/v/unaisulhadi/emojiratingbar.svg)](https://jitpack.io/#unaisulhadi/emojiratingbar)
[![Android Arsenal]( https://img.shields.io/badge/Android%20Arsenal-Emoji%20Rating%20Bar-green.svg?style=flat )]( https://android-arsenal.com/details/1/8293 )
<br/>

#### A simple Emoji Rating Bar library for Android completely written in Kotlin.

 <img src="https://raw.githubusercontent.com/unaisulhadi/EmojiRatingBar/master/art/Rating.png">
 
## 🛠 Installation

Add the JitPack repository to your ```build.gradle``` (Project) file
```bash
allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}
```

Add this line to your ```build.gradle``` (module)
```bash
implementation 'com.github.unaisulhadi:emojiratingbar:1.0.5'
```

## ⌨️ Usage

- Add this in your layout xml file.

```xml
<com.hadi.emojiratingbar.EmojiRatingBar
                android:id="@+id/emoji_rating_bar"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_gravity="center"
                app:showText="true"
                app:showAllText="true"
                app:titleColor="#844848"
                app:defaultValue="AWFUL"
                android:fontFamily="@font/playfair_display_semibold" />
```

- 6 EmojiRatingBar Rate Values
```kotlin
 0. RateStatus.EMPTY
 1. RateStatus.AWFUL
 2. RateStatus.BAD
 3. RateStatus.OKAY
 4. RateStatus.GOOD
 5. RateStatus.GREAT
```

### Parameters

| Explanation                     | Parameter Name          | Type       | Default Value            |
| ------------------------------- | ----------------------- | ---------- | --------------           |
| Set Title Color                 | **titleColor**          | color      | Same as the Emoji Color  |
| Show Only Selected Emoji Title  | **showText**            | boolean    | true                     |
| Show All Emoji Titles           | **showAllText**         | boolean    | false                    |
| Set Default Rate                | **defaultValue**        | enum       | EMPTY                    |
| Set FontFamily                  | **android:fontFamily**  | font       | Android Default          | 

### Use Programmatically

| Explanation                 | Code                        | Parameter            | Return type    |
| --------------------------- | --------------------------- | -------------------- | -------------- |
| Set Title Color             | setTitleColor(color)        | color reference      |                |
| Set Show Title status       | setShowText(true)           | boolean              |                |
| Get Show Title Status       | getShowText()               |                      | boolean        |
| Set Show All Title Status   | setShowAllText()            | boolean              |	            |
| Get Show All Title Status   | getShowAllText()            |               	   | boolean        |
| Set Current Rate            | setCurrentRateStatus(rate)  | enum                 |                |
| Get Current Rate            | getCurrentRateStatus()      |                      | rate           |
| Set Awful Emoji Title       | setAwfulEmojiTitle()        | string               |                |
| Set Bad Emoji Title         | setBadEmojiTitle()          | string               |                |
| Set Okay Emoji Title        | setOkayEmojiTitle()         | string               |                |
| Set Good Emoji Title        | setGoodEmojiTitle()         | string               |                |
| Set Great Emoji Title       | setGreatEmojiTitle()        | string               |                |
| Set Title Font (from res)   | setTypeFace(font)           | font reference       |                |
| Set Title Font (from Asset) | setTypeFaceFromAssets(font) | path to asset        |                |



### Refer code below

- Get current Rate Status of EmojiRatingBar.
```kotlin
emojiRatingBar.getCurrentRateStatus()
```

- Set Rate Status programmatically.
```kotlin
emojiRatingBar.setCurrentRateStatus(RateStatus.GOOD) //SET
```

- Clear selected Emoji by setting EMPTY
```kotlin
emojiRatingBar.setCurrentRateStatus(RateStatus.EMPTY)
```

- Handle no emoji rating is selected
```kotlin
if(emojiRatingBar.getCurrentRateStatus() == RateStatus.EMPTY){
   //Handle if no rating selected
}
```
- Make rating bar read-only (Disable clicks)
```kotlin
emojiRatingBar.setReadOnly(true)
```


- Use OnRateChangeListener for observing Rate Changes
```kotlin
emojiRatingBar.setRateChangeListener(object : EmojiRatingBar.OnRateChangeListener {
            override fun onRateChanged(rateStatus: RateStatus) {
                //Do you Stuff
            }
        })
```
- Do your stuff for separate values
```kotlin
emojiRatingBar.setRateChangeListener(object : EmojiRatingBar.OnRateChangeListener {
            override fun onRateChanged(rateStatus: RateStatus) {
               
               when (rateStatus) {

                    RateStatus.AWFUL -> {
                        //Do your code
                    }
                    RateStatus.BAD -> {
                        //Do your code
                    }
                    RateStatus.OKAY -> {
                        //Do your code
                    }
                    RateStatus.GOOD -> {
                        //Do your code
                    }
                    RateStatus.GREAT -> {
                        //Do your code
                    }
		    RateStatus.EMPTY -> {
                        //Do your code
                    }

                }
            }
})
 ```
 
 - You can use your own Emoji titles
 ```kotlin
 emojiRatingBar.setAwfulEmojiTitle("Awful!")
 emojiRatingBar.setBadEmojiTitle("Bad!")
 emojiRatingBar.setOkayEmojiTitle("Okay!")
 emojiRatingBar.setGoodEmojiTitle("Good!")
 emojiRatingBar.setGreatEmojiTitle("Great!")
 ```
 
 
 ## 🍰  Contribute  

Feel free to fork this project, to optimise the code or to add new features. 

## ✍️ Author
* <b>Unaisul Hadi</b>
* Email: unaisulhadi@gmail.com


## 📝 License

```
MIT License

Copyright (c) 2021 Unaisul Hadi

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
