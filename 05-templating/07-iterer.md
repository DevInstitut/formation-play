# Itérer

La directive `@for` permet d’itérer sur une collection.

```html
<ul>
	@for(s <- speakers) {
	  <li>@s.getFirstname()</li>
	}
</ul>
```

Le caractère `{` doit être sur la même ligne que `@for`.

Dans cet exemple, `speakers` représente une collection d'objet `Speaker`.
