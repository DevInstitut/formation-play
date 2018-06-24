# application.conf

## Taille maximum du corps d’une requête

Les parseurs basés sur du contenu textuel charge en mémoire l’intégralité du corps. Pour éviter qu’une seule requête puisse avoir la possibilité de dégrader les performances, une taille maximum de corps de requête est définie à 100 Ko.

```properties
play.http.parser.maxMemoryBuffer=128K
```

Les parseurs qui utilisent le disque pour stocker des données temporaires (multipart/form-data ou raw), la taille maximum du corps de la requête est fixée par défaut à 10 Mo.
Pour modifier cette valeur par défaut :
```properties
play.http.parser.maxDiskBuffer=15M
```
