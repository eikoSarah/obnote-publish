## 建立SharedPreferences 

```kotlin
val sharedPref = activity?.getPreferences(Context.MODE_PRIVATE)
```




### 其他方式
```kotlin
val sharedPreferences = PreferenceManager.getDefaultSharedPreferences(this /* Activity context */)   // 取得SharedPreference
```

```kotlin
val appContext = requireContext().applicationContext  
var prefs = appContext.getSharedPreferences("mainAccount", Context.MODE_PRIVATE)
```

### 默認儲存路徑
默認會存到這個路徑
`/data/data/com.package.name/shared_prefs/com.package.name_preferences.xml`

也可以自定義名稱來儲存內容。[[getSharedPreferences]]
*[[儲存鍵或值資料#^flc0wy|getDefaultSharedPreferences 也是一種 getSharedPreferences]]*

## 新增或修改資料

```kotlin
val sharedPref = activity?.getPreferences(Context.MODE_PRIVATE) ?: returnwith (sharedPref.edit()) {    
	putInt(getString(R.string.saved_high_score_key), newHighScore)    
	apply()  
}
```


### 其他方式

```kotlin
var editor = sharedPreference.edit()
editor.putString("username","Anupam")
editor.putLong("l",100L)
editor.commit()
```

## 讀取資料


```kotlin
val sharedPref = activity?.getPreferences(Context.MODE_PRIVATE) ?: return  
val defaultValue = resources.getInteger(R.integer.saved_high_score_default_key)  
val highScore = sharedPref.getInt(getString(R.string.saved_high_score_key), defaultValue)
```

### 其他方式
```kotlin
val name = sharedPreferences.get("signature", "")//讀取名稱為signature，預設值為""的String

sharedPreference.getLong("l",1L)
```

## 刪除資料

```kotlin
var editor = sharedPreference.edit()
editor.clear()
editor.remove("username")
```

## 參考資料
### 主要
[保存键值对数据  |  Android 开发者  |  Android Developers](https://developer.android.com/training/data-storage/shared-preferences?hl=zh-cn)

### 其他
[Kotlin 開發第 13 天 LocalStorage（SharedPreferences） - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10191814)

[Day 20 - 使用SharedPreference儲存資料 - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10188441)
注意:此為Java版

[Android SharedPreferences using Kotlin | DigitalOcean](https://www.digitalocean.com/community/tutorials/android-sharedpreferences-kotlin)
有各項範例 