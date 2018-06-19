# Injecter une instance d'acteur via le constructeur


```java
@Singleton
public class MyController extends Controller {

	private ActorRef myActor;

    @Inject 
    public MyController(@Named("my-actor") ActorRef myActor) {
        this.myActor = myActor;
    }

    public CompletionStage<Result> action() {
        ...;
    }
}
```
