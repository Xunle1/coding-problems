# Use Specify Profile Test Spring Boot Test

Use `@TestPropertySource` annotation to specify profile.

`application.yaml`

```yaml
spring:
  profiles:
    active: prod
```

```java
@SprintBootTest
// use application-dev.yaml
@TestPropertySource(properties = {"spring.profiles.active=dev"})
public class TestProfile {
    ...
}
```