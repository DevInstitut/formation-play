# Configuration Play!

Le fichier de configuration d'une application Play! est `conf/application.conf`.

Il est au format HOCON : Human-Optimized Config Object Notation (https://github.com/typesafehub/config/blob/master/HOCON.md).

Play! utilise la librairie Typesafe config (https://github.com/typesafehub/config) pour exploiter ce fichier.

Une configuration initiale est chargée via n'importe quel fichier portant le nom `reference.conf` dans le classpath.
La plupart des JARs de Play! inclut ce fichier pour leurs configuration.
Les propriétés contenues dans les fichiers `reference.conf` peuvent être redéfinies dans le fichier `conf/application.conf`.

Les propriétés du fichier `conf/application.conf` peuvent être redéfinies par les propriétés système.