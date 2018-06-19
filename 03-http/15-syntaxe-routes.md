# Syntaxe routes

## Paramètres d’URI (ex. /speaker/12)
```scala
GET   /speaker/:id controllers.Speakers.getById(id:Long)
```
## Paramètres avec valeur par défaut
```scala
GET   /speaker/ controllers.Speakers.list(page:Int?=1)
GET   /speaker/ controllers.Speakers.list(page:Int?=1, version ?= null)
```

**Une URI peut correspondre à plusieurs routes. La première route déclarée qui correspond est prioritaire.**
