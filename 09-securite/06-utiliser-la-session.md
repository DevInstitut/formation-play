# Utiliser la Session


```java
// Stocker une donnée
session("connected", "rossi.oddet@gmail.com");

// Lire une donnée stockée
session("connected");

// Supprimer une donnée stockée
session().remove("connected");

// Vider la session
session().clear();
```
