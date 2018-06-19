# Entêtes de la réponse

La méthode `response()` retourne un objet réponse qui permet d’en modifier les entêtes.

```java
public Result index() {
	    response().setContentType("text/html");
	    response().setHeader(CACHE_CONTROL, "max-age=3600");
	    response().setHeader(ETAG, "xxx");
	    return ok("<h1>Hello World!</h1>");
}
```
