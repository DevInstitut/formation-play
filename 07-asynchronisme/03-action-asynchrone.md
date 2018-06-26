# Action asynchrone


Par défaut, toutes les actions de Play! sont asynchrones.

Le code exécuté par un contrôleur doit être le plus rapide possible.

Dans le cas où, un traitement long ou bloquant est exécuté, il faut éviter qu'il le soit dans le Thread courant.

Il convient alors de l'exécuter dans un context d'exécution particulier.



Java 8 fournit la classe `java.util.concurrent.CompletionStage<T>` qui permet de modéliser une promesse de résultat.

Play! donne la possibilité d'utiliser le type retour `CompletionStage<Result>` pour inciter les développeurs à réaliser des opérations non bloquantes.

```java
public class MonController {

    public CompletionStage<Result> index() {
        // ... traitements non bloquants
        return // .. promesse de résultat
    }
}
```


