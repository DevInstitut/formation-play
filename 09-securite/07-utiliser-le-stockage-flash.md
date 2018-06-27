# Utiliser le stockage Flash

```java
// Stocker une donnée
flash("success", "données sauvegardées");

// Lire une donnée stockée
flash("success");

// Supprimer une donnée stockée
flash().remove("connected");

// Tout supprimer
flash().clear();
```
