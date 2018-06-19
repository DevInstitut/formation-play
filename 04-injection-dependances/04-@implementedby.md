# @ImplementedBy

L'annotation `com.google.inject.ImplementedBy` fournit par Guice permet de désigner l'implémentation à utiliser pour une interface donnée.

```java
import com.google.inject.ImplementedBy;

@ImplementedBy(EnglishHello.class)
public interface Hello {

    String sayHello(String name);
}

public class EnglishHello implements Hello {

    public String sayHello(String name) {
        return "Hello " + name;
    }
}

```
