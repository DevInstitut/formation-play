# Référentiels

Par défaut, Play utilise :

* Le référentiel Maven Central 
* Le référentiel _TypeSafe Releases_ (https://repo.typesafe.com/typesafe/releases).

Pour ajouter des référentiels :
```scala
resolvers += "mes snapshots" at "https://messnap.fr"

resolvers += (
  "Local Maven" at "file:///"+Path.userHome.absolutePath+"/.m2/repository"
)
```
