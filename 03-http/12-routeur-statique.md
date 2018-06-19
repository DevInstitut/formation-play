# Routeur statique

* Routeur par défaut de Play! < `2.5.x`.

* Activable depuis Play! `v2.5.x` via une configuration du fichier build.sbt :

```scala
routesGenerator := StaticRoutesGenerator
```

* Les routes référencent des méthodes statiques.

```
GET /hello @controllers.HelloController.hello()
```

```java
public class HelloController {

  public static Result hello() { ... }

}
```
