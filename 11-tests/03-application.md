# Test avec un contexte application.

=> Utilisation de la classe `play.test.WithApplication`.

* Créer un test pour la classe `InboxItemServiceJpa` :

```java

public class InboxItemServiceJpaTest extends WithApplication {

    @Test
    public void findAll() throws ExecutionException, InterruptedException {

        InboxItemServiceJpa jpaSvr = instanceOf(InboxItemServiceJpa.class);

        List<InboxItem> inboxItems = jpaSvr.findAll().toCompletableFuture().get();

        // TODO ajouter des assertions
    }

    // TODO tester d'autres méthodes de la classe.
    

}

```