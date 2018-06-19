# Content-type

Le paramètre `content-type` d’une réponse est fixé automatiquement en fonction de la définition du résultat.

```java
ok("Bonjour Play!"); // content-type = "text/plain"
ok(Json.toJson(object)); // content-type = "application/json"
```

Pour spécifier une autre  valeur pour `content-type`, vous pouvez :

* Soit modifier la réponse :

```java
response().setContentType("text/html");
```

* Soit utiliser la méthode `as`

```java
ok("Bonjour Play!").as("text/html"); 
```
