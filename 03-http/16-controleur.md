# Contrôleur

* Un contrôleur est une classe Java qui étend `play.mvc.Controller` et qui contient des actions.

```java

// => Contrôleur
public class Application extends Controller {

    // => Action
    public Result index() {
        // traitement action index
    }

    // => Action
    public Result bonjour(String name) {
        // traitement action bonjour
    }
}
```