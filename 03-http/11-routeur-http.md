# Routeur HTTP

Play! possède un routeur HTTP intégré.

Il permet d’établir une correspondance entre une requête HTTP et une action.

Le routage est défini dans le fichier `conf/routes`. Chaque ligne du fichier a le format :

```
<METHODE> <URI> <ACTION>
```

Play! supporte 2 types de routeur :

* un **routeur statique**. C’est le routeur historique de Play!, les actions sont alors des méthodes statiques.

* un **routeur injecté** (activé par défaut depuis la version 2.5.0) qui permet une injection de dépendances (les actions sont alors des méthodes d’instance).

