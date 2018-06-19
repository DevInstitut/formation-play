# Le caractère @{}
Utiliser des accolades pour exprimer plusieurs instructions 

```html
<body>
    <h1>Page : Hello @{sp.getFirstname() + " " + sp.getLastname(); 
    sp.getEmail();}</h1>
</body>
```
