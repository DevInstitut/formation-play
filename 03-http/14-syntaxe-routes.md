# Syntaxe routes

## Exemple

```scala
GET   /   controllers.Application.index()
```

Trois parties :
* La méthode HTTP (`GET`)
* L’URI (`/`)
* L’action (`controllers.Application.index()`)

## Paramètre avec valeur fixe

```scala
GET /task/:id controllers.Tasks.getById(id:Long, debug:Boolean=false)
```

## Paramètre de chemin (ex. /speaker/12)

```scala
GET   /speaker/:id controllers.Speakers.getById(id:Long)
```


## Paramètre avec valeur par défaut

```scala
GET   /speaker/ controllers.Speakers.list(page:Int?=1)
GET   /speaker/ controllers.Speakers.list(page:Int?=1, version ?= null)
```

**Une URI peut correspondre à plusieurs routes. La première route déclarée qui correspond est prioritaire.**

## Paramètre de chemin contenant `/`

```
GET   /files/*name          controllers.Application.download(name)
```

`GET /files/documents/images/logo.png` => `name = documents/images/logo.png`.

## Paramètre de chemin avec expression régulière

Syntaxe : `$<param><regex>`.

```scala
GET   /speakers/$id<[0-9]+>  controllers.Speakers.show(id: Long)
```

## Paramètre de requête

```
GET /speakers   controllers.Speakers.list(page)
```

Le paramètre `page` peut être passé en paramètre de requête : `GET /speakers?page=1`.

## Types de paramètres

* Pour les paramètres de type `String`, le type est optionnel.

## Le contrôleur `Default`

Play fournit un contrôleur `Default` implémentant quelques actions usuelles : redirection, erreur serveur, ...


```
# Redirige vers https://www.dev.fr/ avec le code 303
GET   /apropos      controllers.Default.redirect(to = "https://www.dev.fr/")

# Répond avec un code 404
GET   /orders     controllers.Default.notFound

# Répond avec 500
GET   /clients    controllers.Default.error

# Répond avec 501 (Non implémenté)
GET   /posts      controllers.Default.todo
```
