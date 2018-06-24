# DynamicForm

La classe `play.data.FormFactory` permet de récupérer les données de formulaire même s'il n’y a pas de modèle dédié.

```java
DynamicForm requestData = formFactory.form().bindFromRequest();

String firstname = requestData.get("firstname");

String lastname = requestData.get("lastname");
```
