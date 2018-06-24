# HOCON - variables

Dans la configuration, il est possible de se référer à une autre partie de la configuration via des variables.

Syntaxe d'une variable de substitutions

```bash
${expression}
${?expression}
```
Exemple

```bash
bar : { foo : 42,
        baz : ${bar.foo}
      }
```
