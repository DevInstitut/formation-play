# Composition des actions

Même en Java, les actions Play! sont définies comme des méthodes de contrôleur, en interne, Play! les gère comme des fonctions.

Java ne supportant pas encore la notion de _classe fonction_, une action fournie par l'API Java est instance de `play.mvc.Action`.

```java
public abstract class Action<T> extends Results {

    public T configuration;
    public Action<?> delegate;
    public abstract CompletionStage<Result> call(Context ctx);
    public static abstract class Simple extends Action<Void> {}

}

```

## Créer une action réutilisable

```java
public class MonAction extends play.mvc.Action.Simple {
    public CompletionStage<Result> call(Http.Context ctx) {

        Logger.info("Exécution de l'action {}", ctx);

        return delegate.call(ctx); // exécution de l'action décorée
    }
}
```

## Décoration d'une action avec @with

```java
@With(MonAction.class)
public Result index() {
    return ok();
}
```

Il est possible de positionner l'annotation sur la classe du contrôleur pour impacter toutes les actions.


## Créer ses annotations

```java
@With(MonAction.class)
@Target({ElementType.TYPE, ElementType.METHOD})
@Retention(RetentionPolicy.RUNTIME)
public @interface MonAnnotation {
    boolean value() default true;
}

public class MonAction extends Action<MonAnnotation> {
    public CompletionStage<Result> call(Http.Context ctx) {
        if (configuration.value()) {
            Logger.info("Exécution de l'action {}", ctx);
        }
        return delegate.call(ctx);
    }
}
```

```java
@MonAnnotation(false)
public Result index() {
    return ok();
}
```