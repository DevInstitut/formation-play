# Récupérer l'instance de l'acteur depuis un contrôleur

Récupérer l'instance de l'acteur depuis un contrôleur grâce à l'injection du système d'acteur Akka (`akka.actors.ActorSystem`).

```java
@Singleton
public class MyController extends Controller {

    final ActorRef myActor;

    @Inject 
    public MyController(ActorSystem system) {
        myActor = system.actorOf(MyActor.props);
    }

    public CompletionStage<Result> action() {
        ...;
    }
}
```
