# Transformer la réponse

```java
// Traiter une réponse sous la forme d'un document JSON.
CompletionStage<JsonNode> jsonPromise = ws.url(url).get()
        .thenApply(WSResponse::asJson);

// Traiter une réponse sous la forme d'un document XML.
CompletionStage<Document> documentPromise = ws.url(url).get()
        .thenApply(WSResponse::asXml);
```

