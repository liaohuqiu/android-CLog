## [中文版文档](https://github.com/liaohuqiu/android-CLog/blob/master/README-cn.md)

# A Simple Log Tool

An encapsulation of `android.util.Log`, which provides:

* Log level control
    You can display different log according different environment.

* Log with parameters
    ```
    CLog.d("sample", "Here is a debug message with parameters: %d", 1);
    ```

# Import to your project

You can copy the source code to your source code directory, it only a single file.

This library has been pushed to Maven Central, you can import it by pom or gradle.

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

# Usage

#### Package

```java
import in.srain.cube.util.CLog;
```

#### Log level

```
public static final int LEVEL_VERBOSE = 0;
public static final int LEVEL_DEBUG = 1;
public static final int LEVEL_INFO = 2;
public static final int LEVEL_WARNING = 3;
public static final int LEVEL_ERROR = 4;
public static final int LEVEL_FATAL = 5;
```

Default log level is `LEVEL_VERBOSE`. The log whose log is lower than log level you set by calling `setLogLevel` will not been printed.

For example, you set log level to `LEVEL_INFO`, the log sent by `CLog.d` or `CLog.v` will not been print.

#### Set log level according to the environment

```
if (environment.equals("production")) {
    // production
    CLog.setLogLevel(CLog.LEVEL_ERROR);
} else if (environment.equals("beta")) {
    // beta
    CLog.setLogLevel(CLog.LEVEL_WARNING);
} else {
    // development
    CLog.setLogLevel(CLog.LEVEL_VERBOSE);
}
```

#### Print log

```
CLog.d("sample", "Here is a debug message");
CLog.d("sample", "Here is a debug message with parameters: %d", 1);
```


# License

Apache 2

# Contact & Help

Please fell free to contact me if there is any problem when using the library.

* srain@php.net
* twitter: https://twitter.com/liaohuqiu
* weibo: http://weibo.com/liaohuqiu
* blog: http://www.liaohuqiu.net
* QQ tribe: 271918140
