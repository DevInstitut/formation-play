# Créer un acteur.

```java
import akka.actor.AbstractActor;

public class MyActor extends AbstractActor {


   @Override
   public Receive createReceive() {

       return receiveBuilder().
               match(TypeDuMessage.class, (leMessage) -> {

                  // traitement du message

               }).build();
   }
}
```
