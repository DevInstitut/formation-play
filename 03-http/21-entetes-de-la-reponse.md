# Entêtes de la réponse

La méthode `response()` retourne un objet réponse qui permet d’en modifier les entêtes.

```java

public class UnControlleur {
     
    public Result index() {
        
        // Modification des entêtes de réponse HTTP
	    response().setContentType("text/html");
	    response().setHeader(CACHE_CONTROL, "max-age=3600");

	    return ok("<h1>Hello World!</h1>");
    }
}
```
