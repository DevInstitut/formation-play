# Formulaire - erreurs

Savoir si un formulaire est valide.

```java
if (userForm.hasErrors()) {
    // … 
}
```

Un objet formulaire peut être utilisé dans un template :

```html
@if(form.hasGlobalErrors) {
<p class="error">@form.globalError.message</p>
}
```
Pour récupérer les erreurs sur un champ donné :

```html
@for(error <- form("email").errors) {
    	<p>@error.message</p>
}
```
