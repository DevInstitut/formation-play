# Paramètres de template

Les paramètres d’entrée du template sont déclarés sur la partie supérieure du template.

```html
@(firstname:String, lastname:String)
<!doctype html>
<html>
  <head>
```

Définir une valeur par défaut :

```html
@(firstname:String = "Paul", lastname:String = "Eric")
<!doctype html>
<html>
  <head>
```

Définir plusieurs groupes de paramètres :

```html
@(firstname:String = "Paul")(body: Html)
<!doctype html>
<html>
  <head>
```
