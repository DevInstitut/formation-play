# Reactive Streams

`Reactive Streams` est une initiative visant à produire un standard pour **le traitement de flux asynchrone**.

Java 9 intègre des interfaces `java.util.concurrent.Flow` (https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/Flow.html).


## La problématique

## Akka Streams

Akka Streams se base sur 4 structures principales :

* `Source` : une source est responsable de la production du flux de données. Elle contient exactement une seule sortie.
* `Sink` : consommateur du flux de données. Il a exactement une seule entrée.
* `Flow` : transformateur de flux de données. Il a exactement une entrée et une sortie.
* `Junction` : une jonction peut avoir plusieurs entrées et plusieurs sorties.

Quand un `Flow` est connecté à la fois à une source et un consommateur, il devient exécutable.
Le processus qui vise à lancer l'exécution d'un `Flow` s'appelle la `matérialisation`.
Quand un `Flow` est `matérialisé`, toutes les ressources nécessaires (buffers, threads, acteurs, ...) sont allouées.
