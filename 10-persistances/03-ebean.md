# EBean

Pour activer EBean :

* Modifier le fichier `project/plugins.sbt` pour ajouter le plugin `sbt-play-ebean` :
```scala
addSbtPlugin("com.typesafe.sbt" % "sbt-play-ebean" % "3.0.0")
```

* Activer le plugin `PlayEBean`
```scala
lazy val myProject = (project in file("."))
    .enablePlugins(PlayJava, PlayEbean)
```


Dans le fichier `conf/application.conf`, spécifier l’emplacement des modèles à traiter par Bean :
```properties
ebean.default = ["models.*"]
```
`default` représente le nom d’une source de données.


Un modèle hérite de `com.avaje.ebean.Model`.

```java
@Entity
public class Task extends Model {
    @Id
    @Constraints.Min(10) public Long id;

    @Constraints.Required public String name;

    public boolean done;

    @Formats.DateTime(pattern="dd/MM/yyyy")
    public Date dueDate = new Date();

    public static Finder<Long, Task> find = 
                  new Finder<Long,Task>(Task.class);
}
```


```java

//Find all tasks
List<Task> tasks = Task.find.all();

//Find a task by ID
Task anyTask = Task.find.byId(34L);

//Delete a task by ID
Task.find.ref(34L).delete();

//More complex task query
List<Task> cocoTasks = Task.find.where()
     .ilike("name", "%coco%")
     .orderBy("dueDate asc")
     .findPagedList(1, 25)
     .getList();
```

Par défaut, toutes les requêtes EBean sont exécutées dans une transaction. 

```java
// Une transaction implicite créée
Task task = Task.find.byId(34L);
// Rollback ou Commit de la transaction

task.done = true;

// Une transaction implicite créée
task.save();
// Rollback ou Commit de la transaction
```

L’annotation `@Transactional` fonctionne avec EBean :

```java
@Transactional
public Result save() {
		…
}
```


Pour gérer la transaction de façon programmatique :

```java
Ebean.beginTransaction();
try {
    Task task = Task.find.byId(34L);
    task.done = true;

    task.save();

    Ebean.commitTransaction();
} finally {
    Ebean.endTransaction();
}
```

Pour gérer la transaction de façon programmatique

```java
Ebean.execute(() -> {

    Task task = Task.find.byId(34L);
    task.done = true;

    task.save();
});
```