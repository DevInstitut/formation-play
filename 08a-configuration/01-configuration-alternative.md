# Configuration Alternative

* Il est possible d'ignorer le fichier `conf/application.conf` et de fournir un fichier alternatif via l'une des propriétés système suivant :

  * `config.resource` : spécifie une ressource dans le classpath.
  * `config.file` : spécifie un chemin vers le système de fichiers.

* La directive `include` permet d'inclure un fichier de configuration dans un autre.

```
include "application"
```
