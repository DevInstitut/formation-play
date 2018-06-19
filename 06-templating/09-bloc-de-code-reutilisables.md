# Bloc de code réutilisable

```html

@printFullname(speaker: models.Speaker) = {
    @speaker.getFirstname() + @speaker.getLastname()
}

<ul>
@for(sp <- speakers) {
  @printFullname(sp)
}
</ul>
```
