# WebSocket - Exemple

```java
public LegacyWebSocket<String> index() {

    return WebSocket.whenReady((in, out) -> {

        // recevoir un message du client
        in.onMessage(System.out::println);

        // détecter la déconnexion du client
        in.onClose(() -> System.out.println("Disconnected"));

        // envoyer un message au client
        out.write("Hello!");

    });
}
```
