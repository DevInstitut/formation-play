# Envoyer du JSON

```java
// poster du JSON
ws.url(url).setHeader("Content-Type", "application/json").post(jsonString);
// ou
ws.url(url).setContentType("application/json").post(jsonString);

// poster du formulaire
ws.url(url).setContentType("application/x-www-form-urlencoded")
           .post("key1=value1&key2=value2");

// poster le type JSON
JsonNode json = Json.newObject()
                    .put("key1", "value1")
                    .put("key2", "value2");
ws.url(url).post(json);
```
