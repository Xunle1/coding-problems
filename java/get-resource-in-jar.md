# Get Resource In JAR

在 Spring Boot 项目中，我尝试读取 `src/main/resource` 目录下的文件，一开始在 IDE 中开发时使用的方法是：

```java
private static final String PATH = Thread.currentThread()
        .getContextClassLoader()
        .getResource("xxx/yyy")
        .getPath();
...
FileInputStream fis = new FileInputStream(PATH);
...
```

在 IDE 中没有任何问题，但是当把项目打包成 JAR 后运行出现了错误：

```
java.io.FileNotFoundException: file:/app/app.jar!/BOOT-INF/classes!/keystore/keystore.jks (No such file or directory)
```

原因是不能通过**文件读取**方式读取文件（此时文件系统中已经没有 `xxx/yyy` 文件），只能通过流读取。解决方法：

```java
InputStream is = Thread.currentThread().getContextClassLoader().getResourceAsStream("xxx/yyy");
```
