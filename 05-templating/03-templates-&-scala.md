# Templates & Scala

Les templates Play! sont de simples fichiers texte contenant un bloc de code Scala.

Ils peuvent générer n'importe quel format textuel : HTML, XML, CSV, ...

Ils sont compilés comme des fonctions Scala standard en suivant une convention de nommage.
Le fichier de template `views/Application/index.scala.html` va produire la classe `views.html.Application.index` avec une méthode `apply()`.

Un template :

```html
@(customer: Customer, orders: List[Order])
<h1>Welcome @customer.name!</h1>
...

```

peut être invoqué depuis du code Scala :

```scala
val content = views.html.Application.index(c, o)
```

