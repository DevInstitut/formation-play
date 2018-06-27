# Test d'une classe simple

* Créer un test unitaire pour la classe `InboxItemServiceHashMap`.

```java
public class InboxItemServiceHashMapTest {

    private InboxItemServiceHashMap service;

    @Before
    public void setUp() throws Exception {
        this.service = new InboxItemServiceHashMap();
    }

    @Test
    public void test_findAll() throws ExecutionException, InterruptedException {

        CompletionStage<List<InboxItem>> all = this.service.findAll();

        List<InboxItem> list = all.toCompletableFuture().get();

        // TODO ajouter une assertion
    }

    @Test
    public void test_save() throws ExecutionException, InterruptedException {
        InboxItem savedItem = this.service.save("new title", "http://newurl.com", "new note").toCompletableFuture().get();

        // TODO ajouter une ou plusieurs assertions
    }
}



```

Pour écrire vos assertions, je recommande AssertJ :

```
libraryDependencies += "org.assertj" % "assertj-core" % "3.10.0" % Test
```