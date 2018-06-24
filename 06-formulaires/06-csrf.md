# CSRF

CSRF = Cross Site Request Forgery.

## Protection Play!

Depuis la version 2.6.x, un filtre CSRF est appliqué par défaut.

Cela veut dire que tout formulaire soumis doit posséder un jeton généré par le serveur pour fonctionner.

### Jeton dans l'url

La fonction `@helper.CSRF` appliqué à un formulaire génère un jeton en paramètre d'URL.

```scala
@import helper._

@form(CSRF(routes.ItemsController.save())) {
    ...
}
```

Exemple de formulaire généré.

```html
<form method="POST" action="/items?csrfToken=1234567890abcdef">
   ...
</form>
```

### Jeton dans un champ caché

```scala
@form(routes.ItemsController.save()) {
    
    @CSRF.formField
    ...
}
```


Exemple de formulaire généré.

```html
<form method="POST" action="/items">
   <input type="hidden" name="csrfToken" value="1234567890abcdef"/>
   ...
</form>
```


En savoir plus : https://www.playframework.com/documentation/2.6.x/JavaCsrf.