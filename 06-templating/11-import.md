# Import

La directive `@import` permet d’importer une classe dans un template.

```html
@import utils._

// résolution absolue
@import _root_.company.product.core._
```

Il est possible de configurer dans le fichier `build.sbt` les _imports_ qui seront accessibles dans tous les templates :

```scala
TwirlKeys.templateImports += "org.abc.backend._"
```

