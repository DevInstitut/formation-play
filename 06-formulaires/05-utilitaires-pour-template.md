# Utilitaires pour template

## <form>

Créer une balise <form> :

```html
@helper.form(action = routes.Speakers.postForm()) {
…
}
```

Créer une balise <form> avec d’autres propriétés :

```html
@helper.form(action = routes.Speakers.postForm(), 'id -> "monFormulaire"){
…
}
```

## <input>

Créer une balise `<input>`
```html
@(myForm: Form[User])

@helper.form(action = routes.Application.submit()) {
    	@helper.inputText(myForm("email"))
    	@helper.inputPassword(myForm("password"))
}
```
Créer une balise `<input>` avec d’autres propriétés
```html
@helper.inputText(myForm("email"), 'id -> "email", 'size -> 30)
```

## @helper.inputText

L'outil `@helper.inputText` génère un code HTML de la forme suivante :

```html
<dl class="error" id="email_field">
    <dt><label for="email">Email:</label></dt>
    <dd><input type="text" name="email" id="email" value=""></dd>
    <dd class="error">This field is required!</dd>
    <dd class="error">Another error</dd>
    <dd class="info">Required</dd>
    <dd class="info">Another constraint</dd>
</dl>
```

Quelques options permettent de personnaliser l'affichage :
```
'_label -> "Custom label"
'_id -> "idForTheTopDlElement"
'_help -> "Custom help"
'_showConstraints -> false
'_error -> "Force an error"
'_showErrors -> false
```
