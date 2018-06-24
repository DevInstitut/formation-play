# Cross Scripting

Play 2 "échappe" le contenu saisie par l'utilisateur.

```html
<!-- Si l'utilisateur saisie cela -->

<script>alert("hello user");</script>

<!-- Play! le transforme en -->
&lt;script&gt;alert(&quot;hello user&quot;);&lt;/script&gt;
```

Pour interprété le code HTML contenu dans les données, utiliser la directive `@Html`.

```html
 <p>@Html(speaker.bio)</p>
 ```
