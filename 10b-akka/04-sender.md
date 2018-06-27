# Communiquer avec l'émetteur

Communiquer avec l'émetteur via la méthode `sender()`.

```java

import akka.actor.AbstractActor;

public class MyActor extends AbstractActor {


   @Override
   public Receive createReceive() {

       return receiveBuilder().
               match(TypeDuMessage.class, (leMessage) -> {
                // envoyer un message à un l'émétteur
               // paramètre 1 = message
               // paramètre 2 = émetteur
               this.sender().tell("done!", self());  

               }).build();
   }
}
```
