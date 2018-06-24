# Action non bloquante

Pour réaliser une action non bloquante, il faut que le retour de celle-ci soit une promesse de résultat et non un résultat.

Java 8 fournit la classe `java.util.concurrent.CompletionStage<T>` qui permet de modéliser une promesse de résultat.

```java
public class MonController {

    public CompletionStage<Result> index() {
        // ... traitements non bloquants
        return // .. promesse de résultat
    }
}
```
