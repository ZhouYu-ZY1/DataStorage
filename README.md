## 简介
这是一个基于 MMKV 和 GSON 的高效 Android 本地存储工具，支持任意数据类型的持久化存储与 JSON 序列化处理。

### MMKV
腾讯开源的高性能键值存储框架：
- 基于 mmap 内存映射技术，提供卓越的读写性能
- 支持多进程安全访问
- 相比 SharedPreferences 性能提升显著

### GSON
Google 官方 JSON 处理库：
- 提供完整的 Java 对象与 JSON 数据双向转换能力
- 支持复杂数据结构的序列化与反序列化

### 依赖配置

在 `app/build.gradle` 文件中添加以下依赖：

```gradle
dependencies {
    // MMKV
    implementation 'com.tencent:mmkv:1.2.16'
    
    // GSON
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