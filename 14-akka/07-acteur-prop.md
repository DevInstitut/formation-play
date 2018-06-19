# Injecter une instance d'acteur via une propriété.



```java
@Singleton
public class MyController extends Controller {

	@Inject @Named("my-actor") ActorRef myActor;

    public CompletionStage<Result> action() {
        ...;
    }
}
```
