# Routeur injecté

* Routeur par défaut de Play! depuis `2.5.x`.

* Activable depuis Play! `v2.4.x` via une configuration du fichier build.sbt :

```scala
routesGenerator := InjectedRoutesGenerator
```

* Les routes référencent des méthodes d'instance.

```
GET /hello controllers.HelloController.hello()
```

```java
public class HelloController {

  public Result hello() { ... }

}
```
