# Communiquer avec l'émetteur

Communiquer avec l'émetteur via la méthode `sender()`.

```java
import akka.actor.Props;
import akka.actor.UntypedActor;

public class MyActor extends UntypedActor {

    // Configuration d'acteur Thread-Safe
    public static Props props = Props.create(MyActor.class);

    public void onReceive(Object msg) throws Exception {
        // envoyer un message à un l'émétteur
        // paramètre 1 = message
        // paramètre 2 = émetteur
        this.sender().tell("done!", self());    
    }
}
```
