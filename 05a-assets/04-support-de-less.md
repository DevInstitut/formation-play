# Support de LESS

Les fichiers LESS sont à positionner dans le répertoire `/app/assets`.

Les fichiers CSS générés sont publiés dans le répertoire `/public`.
Exemple : le fichier `app/assets/stylesheets/main.less` produira un fichier `public/stylesheets/main.css`.

Play! configure automatiquement le fichier `main.less`.

Pour référencer d'autres fichiers, le fichier `build.sbt` peut-être configuré comme suit :

```
includeFilter in (Assets, LessKeys.less) := "foo.less" | "bar.less"
```

## Activer le support de LESS

Ajouter le plugin `sbt-less` (https://github.com/sbt/sbt-less#sbt-less).

```scala
addSbtPlugin("com.typesafe.sbt" % "sbt-less" % "1.0.6")
```

## Exemple d'organisation de fichier LESS

```bash
app
 └ assets
    └ stylesheets
       └ main.less
       └ utils
          └ reset.less
          └ layout.less
```

Fichier `app/assets/stylesheets/main.less` :

```less
@import "utils/reset.less";
@import "utils/layout.less";

h1 {
    color: red;
}
```

Référencement dans un template :
```html
<link rel="stylesheet" href="@routes.Assets.at("stylesheets/main.css")">
```

