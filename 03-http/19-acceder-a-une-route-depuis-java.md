# Accéder à une route depuis Java

Toutes les routes sont compilées en une classe `controllers.routes`.

Exemple de redirection utilisant une route :

```java
public Result index() {
    return redirect(controllers.routes.Application.hello("World"));
}
```
