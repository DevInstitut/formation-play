# Configuration programmatique

Il est possible de configurer programmatiquement `Guice` en créant une classe qui étend `AbstractModule`.

```java
import com.google.inject.AbstractModule;
import com.google.inject.name.Names;

// Etendre AbstractModule
public class Module extends AbstractModule {

    // redéfinir la méthode configure
    protected void configure() {

        // Définition de l'implémentation par défaut de l'interface Hello 
        bind(Hello.class).to(EnglishHello.class);

    }
}
```
