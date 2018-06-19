# @Inject

L'annotation `@Inject` peut être utilisée sur un champ.

```java

import javax.inject.*;
import play.libs.ws.*;

public class MonComposant {
    @Inject WSClient ws;

    // ...
}
```

L'annotation `@Inject` peut être également utilisée sur un constructeur.

Cette seconde approche est recommandée pour faciliter les tests.

```java
import javax.inject.*;
import play.libs.ws.*;

public class MonComposant {
    
    private final WSClient ws;

    @Inject
    public MonComposant(WSClient ws) {
        this.ws = ws;
    }

    // ...
}
```
