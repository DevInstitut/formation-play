# JPA

## Configuration

Ajouter les dépendances suivantes :
```scala
libraryDependencies ++= Seq(
  javaJpa,
  "org.hibernate" % "hibernate-entitymanager" % "4.3.9.Final"
)
```

Ajouter un fichier persistence.xml dans le répertoire `conf/META-INF` :
```xml
<persistence ... version="2.1">

<persistence-unit name="defaultPersistenceUnit" 
    transaction-type="RESOURCE_LOCAL">
    <provider>org.hibernate.jpa.HibernatePersistenceProvider</provider>
    <non-jta-data-source>DefaultDS</non-jta-data-source>
    <properties>
        <property name="hibernate.dialect" 
            value="org.hibernate.dialect.H2Dialect"/>
    </properties>
</persistence-unit>

</persistence>
```

Définir l’unité de persistance à utiliser par Play! Framework dans le fichier `conf/application.conf` :
```properties
jpa.default=defaultPersistenceUnit
```

## JPAApi

Pour récupérer une instance d’`EntityManager`, utiliser la classe utilitaire `play.db.jpa.JPAApi` : 

```java
import play.db.jpa.JPAApi;

import javax.inject.*;
import javax.persistence.*;
import java.util.concurrent.*;

@Singleton
public class JPARepository {
    private JPAApi jpaApi;
    private DatabaseExecutionContext executionContext;

    @Inject
    public JPARepository(JPAApi api, DatabaseExecutionContext executionContext) {
        this.jpaApi = api;
        this.executionContext = executionContext;
    }
    
    public CompletionStage<Long> runningWithTransaction() {
        return CompletableFuture.supplyAsync(() -> {

            return jpaApi.withTransaction(entityManager -> {
                Query query = entityManager.createNativeQuery("select max(age) from people");
                return (Long) query.getSingleResult();
            });
        }, executionContext);
    }
    
    
}
```

Source : https://www.playframework.com/documentation/2.6.x/JavaJPA

