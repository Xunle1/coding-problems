# Inject Static Component Into Spring Component

`foo.java`

```java
@Component
public class Foo {}
```

`bar.java`

```java
@Component
public class Bar {

    static Foo foo;

    @Autowired
    public void setFoo(Foo foo) {
        Bar.foo = foo;
    }
}
```
