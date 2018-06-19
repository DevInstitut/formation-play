# Action

* Une action, au sens Play!, est une méthode Java d'un contrôleur qui traite une requête HTTP pour en produire une réponse.

```java
 public Result bonjour() {
      return ok("bonjour");
  }
```

* Le résultat est de type `play.mvc.Result`.

Ce dernier est utilisé pour représenter une réponse HTTP.

* La méthode `ok(String)` produit une réponse :
  * avec le code HTTP 200
  * dont le corps contient la chaîne de caractères en paramètre
