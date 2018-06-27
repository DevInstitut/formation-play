# Composer plusieurs requêtes

```java
// Composer plusieurs requêtes
final CompletionStage<WSResponse> resp = ws.url(urlOne).get()
        .thenCompose(responseOne -> ws.url(responseOne.getBody()).get())
        .thenCompose(responseTwo -> ws.url(responseTwo.getBody()).get());
```

