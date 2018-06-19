# Résultat

* Un résultat représente une réponse HTTP

* Play! fournit des résultats usuels :

  * **play.mvc.Result** : accès aux entêtes, aux cookies, …

  * La classe **play.mvc.Results** aide à la construction de réponse HTTP

* Exemple de réponses :

```java
ok("Bonjour Play!"); // code HTTP 200

redirect("/v2/hello"); // code HTTP 303

forbidden("authentification requise"); // code HTTP 401
```
