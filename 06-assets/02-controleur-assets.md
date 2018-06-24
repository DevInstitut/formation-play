# Contrôleur Assets

Play! vient avec un contrôleur interne `controllers.Assets` dédié aux ressources statiques.

Ce contrôleur fournit :

* Un mécanisme de cache

* Un support ETag

* Un support de la compression gzip

Exemple d’utilisation dans la définition des routes

```
GET /javascripts/*file controllers.Assets.at(path="/p/javascripts", file)
GET /images/*file controllers.Assets.at(path="/p/images", file)
GET /assets/*file controllers.Assets.versioned(path="/p", file: Asset)
```
