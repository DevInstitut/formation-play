# Configurer le parseur de corps de requête

## Configurer un parseur spécifique

```java
@BodyParser.Of(BodyParser.Json.class)
public Result index() {
    RequestBody body = request().body();
    return ok("Got json: " + body.asJson());
}
```

## Limiter la taille du corps

```java
@BodyParser.Of(value = BodyParser.Json.class, maxLength=10*1024)
public Result test() {
  ...
}
```
