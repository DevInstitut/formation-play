# WebJars

Les WebJars sont des ressources statiques (js, css, images, …) assemblées dans un JAR (Java Archive).

Ils offrent la possibilité de gérer les dépendances Web (JQuery, Bootstrap, …) avec les outils de construction comme Maven, Gradle, SBT, …

Les WebJars sont déployés dans Maven Central ou autres dépôts Maven.

Exemple

```scala
libraryDependencies ++= Seq(
  "org.webjars" % "bootstrap" % "4.1.1"
)
```

Pour chercher un WebJar : http://www.webjars.org/

Lorsqu’une dépendance WebJars est déclarée, elle est automatiquement déployée dans un  répertoire `lib`.
