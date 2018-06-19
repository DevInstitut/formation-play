# Agencement

Un template est une fonction qui peut être appelée depuis un autre.

```html
<!-- views/main.scala.html -->
@(title: String)(content: Html)
<!DOCTYPE html>
<html>
  <head><title>@title</title></head>
  <body>
    <section class="content">@content</section>
  </body>
</html>
```

```html
<!-- views/index.scala.html -->
@main(title = "Accueil") {
  <h1>Page Accueil</h1>
}
```
