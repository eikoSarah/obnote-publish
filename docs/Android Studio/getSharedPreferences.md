## 建立

```kotlin
val profilePreferences = getSharedPreferences("profile", Context.MODE_PRIVATE) val profileEditor = profilePreferences.edit() profileEditor.putString(name, "login_name")
```

### Context.MODE
-   Context.MODE_PRIVATE - 代表該檔案為私有檔案，只能被 App 本身存取。
-   Context.MODE_APPEND - 會檢查檔案是否存在，檔案存在會將新的內容新增到檔案內，否則建立新檔案。
-   ~~Context.MODE_WORLD_READABLE (已棄用) - 其他 App 也可以讀取。~~
-   ~~Context.MODE_WORLD_WRITEABLE (已棄用)  - 其他 App 也可以寫入。~~

>   存取模式也可以混著使用，如：  
     `MODE_WORLD_READABLE + MODE_WORLD_WRITEABLE` : 表示其它程式可讀取寫入


## 參考資訊
[Kotlin 開發第 13 天 LocalStorage（SharedPreferences） - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10191814)