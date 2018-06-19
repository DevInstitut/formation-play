# JDBC

Pour configurer Play! pour utiliser JDBC :

Ajouter la dépendance vers JavaJDBC dans le fichier `build.sbt`.
```scala
libraryDependencies += javaJdbc
```

Configurer les sources de données dans le fichier `conf/application.conf`. La source de données par défaut s’appelle `default`. 

Exemple de configuration :

```properties
db.default.driver=org.h2.Driver
db.default.url="jdbc:h2:mem:play"
db.default.username=sa
db.default.password=""
```

## Configurer plusieurs sources de données

```properties
# Orders database
db.orders.driver=org.h2.Driver
db.orders.url="jdbc:h2:mem:orders"

# Customers database
db.customers.driver=org.h2.Driver
db.customers.url="jdbc:h2:mem:customers"
```

## Driver

Play! fournit le driver pour communiquer à une base de données H2. 

Pour toute autre base de données, le driver correspondant à la base de données doit être ajouté.

Exemple pour MySQL :

```scala
libraryDependencies += "mysql" % "mysql-connector-java" % "5.1.18"
```

## Outil `play.db.Database`

Pour accéder à la base de données, injecter un bean de type `play.db.Database`.

```java

// Pour la base de données par défaut
@Inject private Database db;
```

```java

    // Pour les autres
    private Database db;
    
    @Inject
    public JavaNamedDatabase(@NamedDatabase("orders") Database db) {
      this.db = db;
    }

```

```java
// Obtenir une connexion JDBC
Connection co1 = db.getConnection();

```

## Pool de connexion

Play! fournit 2 implémentations de pool de connexion : 

* HikariCP (https://brettwooldridge.github.io/HikariCP/) - pool de connexion par défaut.

* BoneCP (http://www.jolbox.com/)

Le pool de connexion est configurable dans le fichier `conf/application.conf`. 

Les paramètres possibles : https://www.playframework.com/documentation/2.5.x/resources/confs/play-jdbc/reference.conf
