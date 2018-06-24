# Livrable Play!

Utiliser la commande `dist` pour générer le livrable Play!.

Cette commande produit un fichier zip qui contient tous les composants nécessaires à l'exécution d'une application Play!.
```bash
[focused-mind] $ dist
...
...
...
[info] Your package is ready in /..../focused-mind-1.0-SNAPSHOT.zip

```

Le livrable généré par la commande `dist` contient les éléments suivants :

```bash
/focused-mind-1.0-SNAPSHOT
    README
    /bin --> contient des exécutables 
    /conf --> répertoire conf du projet
    /lib --> tous les jars nécessaires
    /share --> la documentation
```
