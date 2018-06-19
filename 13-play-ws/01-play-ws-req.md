# Créer une requête

```java
// Créer une requête
WSRequest request = ws.url("http://monsite.com");

// Mettre à jour les paramètres de la requêtes
WSRequest complexRequest = request.setHeader("headerKey", "headerValue")
                            .setRequestTimeout(1000)
                            .setQueryParameter("paramKey", "paramValue");

// Déclencher la requête de manière asynchrone
CompletionStage<WSResponse> responsePromise = complexRequest.get();

```
