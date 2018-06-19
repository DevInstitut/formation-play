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

Play! fournit une annotation `@play.db.jpa.Transactional` qui permet de rendre transactionnel une action :
```java
@Transactional (readOnly = true)
public Result list() {
		…
}

@Transactional
public Result save() {
		…
}
```

## Utilisation

Pour récupérer une instance d’`EntityManager`, utiliser la classe utilitaire `play.db.jpa.JPAApi` : 

```java
@Inject JPAApi jpaApi;

jpaApi.em().find(Speaker.class, id);

jpaApi.withTransaction(() -> {
    EntityManager em = jpaApi.em();
    Query query = em.createNativeQuery("update speaker set active = 1 where age > 18");
    query.executeUpdate();
});
```
