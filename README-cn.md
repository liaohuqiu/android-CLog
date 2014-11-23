# 简单的日志工具

对`android.util.Log`进行简单的封装, 提供以下功能

* 日志级别控制
    开发测试环境打印所有日志，内测包打印警告和报错日志，线上包只打印crash日志。

* 带参数打印
    ```
    CLog.d("sample", "Here is a debug message with parameters: %d", 1);
    ```

# 引入到项目

只有一个文件，所以你可以直接使用源码，放到你项目中。

这个小类库也发布到了Maven中央库，可以通过pom或者gradle引入。

#### Maren

```xml
<dependency>
    <groupId>in.srain.cube</groupId>
    <artifactId>clog</artifactId>
    <type>jar</type>
    <version>1.0.2</version>
</dependency>
```

#### Gradle

``` groovy
compile 'in.srain.cube:clog:1.0.2'
```

# 使用

#### Package

```java
import in.srain.cube.util.CLog;
```

#### 日志级别

```
public static final int LEVEL_VERBOSE = 0;
public static final int LEVEL_DEBUG = 1;
public static final int LEVEL_INFO = 2;
public static final int LEVEL_WARNING = 3;
public static final int LEVEL_ERROR = 4;
public static final int LEVEL_FATAL = 5;
```

默认是 `LEVEL_VERBOSE`，低于设定级别的日志将不会被打印。
比如: 设定为: `LEVEL_INFO`, `CLog.d`, `CLog.v`的日志将不会执行。

#### 根据不同环境设置不同的日志级别


```
if (environment.equals("production")) {
    // 线上环境
    CLog.setLogLevel(CLog.LEVEL_ERROR);
} else if (environment.equals("beta")) {
    // 内测环境
    CLog.setLogLevel(CLog.LEVEL_WARNING);
} else {
    // 开发环境
    CLog.setLogLevel(CLog.LEVEL_VERBOSE);
}
```

#### 打印日志

```
CLog.d("sample", "Here is a debug message");
CLog.d("sample", "Here is a debug message with parameters: %d", 1);
```


# License

Apache 2

# 联系方式和问题反馈

* srain@php.net
* twitter: https://twitter.com/liaohuqiu
* weibo: http://weibo.com/liaohuqiu
* blog: http://www.liaohuqiu.net
* QQ tribe: 271918140
