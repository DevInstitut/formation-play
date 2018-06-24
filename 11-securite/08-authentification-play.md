# Authentification Play! 

Play! fournit une action composable `Security.Authenticator` que nous pouvons étendre afin d'ajouter notre logique.

Exemple d'implémentation.

```java
public class Secured extends Security.Authenticator {
    @Override
    public String getUsername(Context ctx) {
        return ctx.session().get("email");
    }
    @Override
    public Result onUnauthorized(Context ctx) {
        return redirect(routes.Application.login());
    }
}
```
Sécuriser ensuite des contrôleurs et des actions.

```java
@Security.Authenticated(Secured.class)
public class TodoController extends Controller {

	public Result index() {
		return ok(views.html.todo.render());
	}
}
```

