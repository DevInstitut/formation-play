# Cookie

La méthode `response().setCookie` permet de d’ajouter un cookie à la réponse.

```java
response().setCookie("theme", "principal");
```


Pour une configuration plus fine :
```java
response().setCookie(
	        "theme",        // nom du cookie
	        "principal",    // valeur
	        3600,           // age maximum
	        "/some/path",   // path
	        ".example.com", // domaine
	        false,          // sécurisé
	        true            // uniquement http
);
```

Pour supprimer un cookie :
```java
response().discardCookie("theme");
```

