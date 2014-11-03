### A Simple Log Tool

An encapsulation of `android.util.Log`, which provides:

* Log level control

    You can display different log according different environment.

* Log with parameters

#### Marven

```xml
<dependency>
    <groupId>in.srain.cube</groupId>
    <artifactId>clog</artifactId>
    <type>jar</type>
    <version>1.0.1</version>
</dependency>
```

#### Gradle

``` groovy
compile 'in.srain.cube:clog:1.0.1'
```

#### Package

```java
import in.srain.cube.util.CLog;
```

### Usage

#### Log level

```
public static final int LEVEL_VERBOSE = 0;
public static final int LEVEL_DEBUG = 1;
public static final int LEVEL_INFO = 2;
public static final int LEVEL_WARNING = 3;
public static final int LEVEL_ERROR = 4;
public static final int LEVEL_FATAL = 5;
```

Default log level is `LEVEL_VERBOSE`.

#### Set log level according to the environment

```
if (environment.equals("production")) {
    CLog.setLogLevel(CLog.LEVEL_ERROR);
} else if (environment.equals("beta")) {
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


### License

Apache 2

### Contact & Help

Please fell free to contact me if there is any problem when using the libray.

* srain@php.net
* twitter: https://twitter.com/liaohuqiu
* weibo: http://weibo.com/liaohuqiu
* blog: http://www.liaohuqiu.net
* QQ tribe: 271918140
