# Encodage des caractères

Pour un résultat texte, il est important de spécifier l'encodage utilisé.

Play! utilise par défaut l'encodage UTF-8.

L'encode peut-être spécifié :

* Soit sur l'objet réponse.

```java
response().setContentType("text/html; charset=iso-8859-1");
```

* Soit directement lors de la construction du résultat.

```java
ok("<h1>Hello World!</h1>", "iso-8859-1");
```
