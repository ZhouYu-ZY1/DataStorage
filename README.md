## 简介

这是一个基于 MMKV 和 GSON 依赖库封装的 Android 存储工具，用于高效的本地数据存储和 JSON 数据处理。

### MMKV
MMKV 是腾讯开源的高性能移动端通用存储方案，基于 mmap 内存映射技术，具有高性能、高可靠性等特点。

### GSON
GSON 是 Google 提供的用于在 Java 对象和 JSON 数据之间进行映射的库。

### 依赖配置

在 `app/build.gradle` 文件中添加以下依赖：

```gradle
dependencies {
    // MMKV - 高性能键值存储
    implementation 'com.tencent:mmkv:1.2.16'
    
    // GSON - JSON 序列化/反序列化
    implementation 'com.google.code.gson:gson:2.10.1'
}
```

## 支持直接存储任意类型，并获取对象
```kotlin
DataStorage.put("string", "qwertyuiop")
val string = DataStorage.get("string", "")

DataStorage.put("List", ArrayList<String>())
// 必须传入默认值不能为null,默认值类型用于判断返回值类型
val list = DataStorage.get("userData", ArrayList<String>())

DataStorage.put("user",User("aaa","123","000"))
val user = DataStorage.get("user", User()) 
```