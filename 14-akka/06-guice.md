# Acteur et Guice

Il est possible de rendre injectable directement une instance d'acteur via une configuration de module Guice.

```java
// Implémenter l'interface import play.libs.akka.AkkaGuiceSupport;
public class Module extends AbstractModule implements AkkaGuiceSupport {

    @Override
    public void configure() {

        // rendre injectable un acteur
        bindActor(MyActor.class, "my-actor");
    }

}

```
