# Le caractère @

Le caractère `@` est utilisé pour délimiter du contenu dynamique.

Pour écrire le caractère `@`, utiliser `@@`.

```html
<body>
    <h1>Page : Hello @name</h1>
</body>
```

Utiliser des parenthèses pour exprimer des expressions plus complexes :

```html
<body>
    <h1>Page : Hello @(sp.getFirstname() + " " + sp.getLastname())</h1>
</body>
```
