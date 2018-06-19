# Syntaxe routes

## Exemple

```scala
GET   /   controllers.Application.index()
```

Trois parties :
* La méthode HTTP (`GET`)
* L’URI (`/`)
* L’action (`controllers.Application.index()`)

## Paramètres avec valeur fixe

```scala
GET /task/:id controllers.Tasks.getById(id:Long, debug:Boolean=false)
```
