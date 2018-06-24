# HOCON <> JSON

* Un fichier HOCON ne commence pas par `[` ou `{` comme le format JSON.

Le contenu est directement interprété comme s'il était encadré de `{` et `}`.

* L'affectation d'une valeur peut se faire avec `=` ou `:`.

* Si la valeur d'une propriété est un objet (début par `{`), alors les caractères `=` ou `:` peuvent être omis.

.left-column[
```
cle1 : {
  cle2: "val2"
}
```
]
.right-column[
```
cle1 {
  cle2: "val2"
}
```
]
