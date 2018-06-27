# Récupérer l'instance de l'acteur depuis un contrôleur

Récupérer l'instance de l'acteur depuis un contrôleur grâce à l'injection du système d'acteur Akka (`akka.actors.ActorSystem`).

```java
public class MyController extends Controller {

    private ActorRef createTodoActor;

    @Inject 
    public MyController(@Named("NOM_ACTEUR") ActorRef createTodoActor) {
        this.createTodoActor = createTodoActor;
    }

    public CompletionStage<Result> action(String parametre) {
        
        Future<Object> actorResponse = Patterns.ask(createTodoActor, parametre, 10000);


        return FutureConverters.toJava(actorResponse)
                .thenApplyAsync(response -> redirect(routes.TodoController.index()), httpExecutionContext.current());

    }
}
```
