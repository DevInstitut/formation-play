# Contrôleur

* Un contrôleur est une classe Java qui étend `play.mvc.Controller` et qui contient des actions.

```java
public class Application extends Controller {

    public Result index() {
        // traitement action index
    }

    public Result bonjour(String name) {
        // traitement action bonjour
    }
}
```