
# Evolutions

Play! fournit un module de migration de base de données.

Ajouter la dépendance vers evolutions dans le fichier `build.sbt`:
```scala
libraryDependencies += evolutions
```

Utiliser Evolutions consiste à créer un ensemble de scripts SQL.

Les scripts sont placés dans le répertoire `conf/evolutions/<nom_bdd>` (par exemple `conf/evolutions/default`). Le premier script est nommé `1.sql`, puis `2.sql`, etc…

Chaque script possède deux parties :

* Ups : les modifications de base de données à appliquer

* Downs : instructions de retour arrière


```sql
# Users schema
 
# --- !Ups
   
CREATE TABLE User (
  id bigint(20) NOT NULL AUTO_INCREMENT,
  email varchar(255) NOT NULL,
  password varchar(255) NOT NULL,
  fullname varchar(255) NOT NULL,
  isAdmin boolean NOT NULL,
  PRIMARY KEY (id)
);

# --- !Downs

DROP TABLE User;
```
