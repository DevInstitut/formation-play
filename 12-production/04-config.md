# Configuration

* Fournir un fichier de Configuration.

```bash
# soit via -Dconfig.resource si le fichier
# est dans le classpath
$ /path/to/bin/<project-name> -Dconfig.resource=prod.conf

# soit via -Dconfig.file si le fichier
# se trouve ailleurs sur le disque
$ /path/to/bin/<project-name> -Dconfig.file=/opt/conf/prod.conf
```

* Configurer l'application via des propriétés systèmes.

```bash
$ /path/to/bin/<project-name> -Ddb.default.password=toto
```

* Configurer le numéro de port.

```bash
$ /path/to/bin/<project-name> -Dhttp.port=80
```

* Configurer la JVM soit dans le script de lancement soit via des propriétés.

```bash
$ /path/to/bin/<project-name> -J-Xms128M -J-Xmx512m -J-server
```
