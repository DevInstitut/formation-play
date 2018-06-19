# Anatomie d’un projet Play! 2

/ : la racine de l’application

/README : un fichier de description de l’application.

/app : le code source de l’application.

**/build.sbt : script SBT de construction.**

/conf : les fichiers de configuration

/dist : fichiers à ajouter lors de la distribution.

**/project : d’autres configurations SBT de la construction du projet.**

/public : ressources statiques non protégées

/test : code de test

## Répertoire /app

```
app                      → Sources de l'application
 └ assets                → Sources à compiler
    └ stylesheets        → Sources LESS
    └ javascripts        → Sources CoffeeScript
 └ controllers           → Contrôleurs
 └ models                → Couche métier
 └ views                 → Templates
```

## Répertoire /conf

Fichiers de configuration (ressources non compilées).

```bash
conf                     
 └ application.conf      → Configuration principale
 └ routes                → Définitions des routes
```

# Répertoire /dist

Ressources à inclure lors de la livraison de l'application.

```bash
dist                     
```

# Répertoire /public

Ressources publiques (CSS, JS, images, ...).

```bash
public                   
 └ stylesheets           → Fichiers CSS
 └ javascripts           → Fichiers JavaScript
 └ images                → Fichiers image
```

# Répertoire /project

Configuration SBT du projet.

```bash
project                  
 └ build.properties      → Propriétés du projet
 └ plugins.sbt           → Configuration des plugins
```

# Répertoire /lib

Librairies utilisées dans le projet non issues d'un référentiel (Maven, Ivy, ...)

```bash
lib                   
```
# Répertoire /logs

Répertoire de logs.

```bash
logs                     
 └ application.log       → Log par défaut
```

# Répertoire /target

```bash
target              → Elements générées par Play!
 └ resolution-cache → Informations dépendances
 └ scala-2.11
    └ api           → Documentation générée
    └ classes       → Classes compilées
    └ routes        → Sources générées des routes
    └ twirl         → Sources générées des templates
 └ universal        → Packaging
 └ web              → Assets compilés
```

# Répertoire /test

Répertoire source pour les tests unitaires et d'intégration.

```bash
test                 
```

# Fichier project/build.properties

```properties
sbt.version=1.0.4
```

# Fichier project/plugins.sbt

```scala
// The Play plugin
addSbtPlugin("com.typesafe.play" % "sbt-plugin" % "2.6.15")
```

# Fichier build.sbt

```scala
name := """focused-mind"""
organization := "dev"

version := "1.0-SNAPSHOT"

lazy val root = (project in file(".")).enablePlugins(PlayJava)

scalaVersion := "2.12.4"

libraryDependencies += guice
```


