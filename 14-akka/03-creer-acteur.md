# Créer un acteur.

```java
import akka.actor.Props;
import akka.actor.UntypedActor;

public class MyActor extends UntypedActor {

    public static Props props = Props.create(MyActor.class);

    public void onReceive(Object msg) throws Exception {
       // traitement du message
    }
}
```
