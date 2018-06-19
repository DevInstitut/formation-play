# Parseur de corps de requête

Play! fournit plusieurs passeurs usuels permettant de récupérer les données de corps de requête.

* Récupérer le corps d’une requête

```java
RequestBody body = request().body();
```

Par défaut, le passeur `AnyContent` est utilisé. 

Suivant l’entête `content-type` de la requête :

* `text/plain` : `body.asText()` retourne une `String`.
* `application/json` : `body.asJson()` retourne un objet `JsonNode`.
* `application/xml`, `text/xml` ou `application/XXX+xml` : `body.asXML()` retourne un objet `org.w3c.Document`
* `application/form-url-encoded` : `body.asFormUrlEncoded()` retourne un objet `Map<String, String[]>`
* `multipart/form-data` : `body.asMultipartFormData()` retourne un objet `Http.MultipartFormData()`
* Autres : `body.asRaw()` retourne un objet `Http.RawBuffer`

