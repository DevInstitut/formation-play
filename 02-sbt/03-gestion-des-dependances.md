# Gestion des dépendances

Play permet d’ajouter des dépendances provenant d’un référentiel ou non.

Si la dépendance à ajouter ne provient pas d’un référentiel, il suffit de créer un répertoire lib et y placer la dépendance (.jar). Elle sera alors **automatiquement prise en compte dans le projet**. Aucune modification du fichier build.sbt n’est requis.

Si la dépendance provient d’un référentiel, le fichier build.sbt doit être complété. Exemple de configuration :

```scala
libraryDependencies += "org.apache.derby" % "derby" % "10.11.1.1"

libraryDependencies += "org.apache.derby" % "derby" % "10.11.1.1" % "test"

libraryDependencies ++= Seq(
  "org.apache.derby" % "derby" % "10.11.1.1",
  "org.hibernate" % "hibernate-entitymanager" % "4.3.9.Final"
)
```
