# Pools de thread

Play! utilise 2 familles de pool de thread :

* `Pools de thread internes` : utilisés en interne pour gérer les entrées/sorties.

* `Pool de thread Play` : utilisé pour le code écrit par le développeur. Il s'agit ici d'un dispatcher Akka utilisé par l'ActorSystem de l'application.

