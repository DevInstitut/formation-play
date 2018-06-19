# Cycle de vie des composants

Le système d'injection de dépendances gère le cycle de vie des composants :

* Une nouvelle instance est créée à chaque fois qu'un composant en a besoin.

Si un composant est injecté plusieurs fois, plusieurs instances seront créées.

* Les instances sont créées au moment où elles sont utilisées (donc pas au démarrage de l'application).

* Play! fournit une instance de type `play.inject.ApplicationLifecycle` qui offre la possibilité d'ajouter des intercepteurs sur les événements liés à la vie des composants.

```java
// Le mécanisme des événements est adapté pour les composants singleton.
// Cela évite d'ajouter un écouteur par instance créée.
@Singleton
public class MonComposant {

    @Inject public MonComposant(ApplicationLifecycle lifecycle) {
        
        // ...

        lifecycle.addStopHook(() -> {
            // code à exécuter lorsque l'application s'arrête.
            // par exemple : libération des ressources systèmes 
            // (connexion base de données, système de fichiers, ...)
            ...
        });
    }
    // ...
}
```