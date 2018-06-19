# Contrôleur Assets

Exemple d’utilisation dans un template :

```html
<script src="@routes.Assets.at("/javascripts/jquery.js")">
</script>

<img src="@routes.Assets.at("/images/logo.png")" />

<script type='text/javascript' 
  src='@routes.Assets.versioned("lib/jquery/jquery.js")'></script>
```
