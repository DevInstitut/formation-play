# package `play.data`

Le package `play.data` contient des utilitaires pour gérer les formulaires dans une application Web.

Soit un bean `User` : 

```java
public class User {
	public String email;
	public String password;
}
```

Récupérer une instance de formulaire (classe `play.data.Form`).

Injecter au préalable, une instance de type `play.data.FormFactory`.

```java
Form<User> userForm = formFactory.form(User.class);
```

Transformer une Map en objet : 

```java
Map<String,String> data = new HashMap<>();
data.put("email", "bob@gmail.com");
data.put("password", "secret");

User user = userForm.bind(data).get();
```

Récupérer les données d'un formulaire depuis la requête :

```java
User user = userForm.bindFromRequest().get();
```

