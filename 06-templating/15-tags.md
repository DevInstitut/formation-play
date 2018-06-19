# Tags

Les _tags_ sont des templates (en réalité de simples fonctions) réutilisables dans d'autres templates.

```html
<!-- views/tags/notice.scala.html -->
@(goodResult: Boolean = false)(body: (String) => Html)
@if(goodResult) {
 <p class="success">@body("green")</p>
} else {
  <p class="error">@body("red")</p>
}

<!-- A l'utilisation dans un autre template -->
@(result: Boolean)
@import tags._

@notice(result) { color =>
  Oops, something is <span style="color:@color">wrong</span>
}
```
