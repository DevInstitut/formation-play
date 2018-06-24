
# Agencement
```html
<!-- views/main.scala.html -->
@(title: String)(sidebar: Html)(content: Html)
<!DOCTYPE html>
<html>
  <head><title>@title</title></head>
  <body>
    <section class="content">@content</section>
    <section class="sidebar">@sidebar</section>
  </body>
</html>
```
```html
<!-- views/index.scala.html -->
@main("Home") {
  <h1>Sidebar</h1>
} {
  <h1>Home page</h1>
}
```
