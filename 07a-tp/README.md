# TP #7 - CompletionStage

* Modifier l'interface `InboxItemService` comme suit :

```java
public interface InboxItemService {

    CompletionStage<List<InboxItem>> findAll();

    CompletionStage<InboxItem> save(String title, String url, String note);
}

```

* Adapter le code existant pour que l'application entière compile et fonctionne.

* Modifier toutes les méthodes de l'interface pour que le type retour soit `CompletionStage<>`.
