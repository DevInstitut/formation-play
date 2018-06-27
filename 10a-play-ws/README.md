# Play WS

Play! propose une librairie permettant d'effectuer des requêtes HTTP non bloquantes.

Pour l'utiliser, ajouter la dépendance javaWS :

```scala
libraryDependencies ++= Seq(
  javaWs
)
```

Dans un contrôleur, injecter une instance de `play.libs.ws.WSClient`.

```java
public class MonController extends Controller {

    @Inject WSClient ws;
    ...
}
```

