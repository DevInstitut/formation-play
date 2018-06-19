# Objet `routes`

Un objet `routes` est accessible dans tous les templates.

Il permet de générer un lien en se basant sur une action plutôt qu'une URL.

```html
<a href="@routes.MonController.monAction()">Effectuer mon action</a>
```
