# Validation

La classe `play.data.validation.Constraints` contient des annotations de validation.

Exemple :

```java
public class User {
	
	@Required
	public String email;
	
	@MaxLength(10)
	public String password;
}
```

## Définir une méthode de validation

Via la méthode `validate()` qui est invoquée si toutes les validations d’annotations ont été passées.

La méthode `validate()` peut retourner les types : `String`, `List<ValidationError>` et `Map<String, List<ValidationError>>`.

Retourner `null` si la validation est ok.

```java
public class User {
	
	public String email;
	public String password;
	
	public String validate() {
        if (authenticate(email, password) == null) {
            return "Email ou Mot de passe invalide";
        }
        return null;
    }
}
```

# Autre exemple

```java
public List<ValidationError> validate() {
  List<ValidationError> errors = new ArrayList<ValidationError>();
  if (User.byEmail(email) != null) {
      errors.add(new ValidationError("email", "This e-mail is exist."));
  }
  return errors.isEmpty() ? null : errors;
}
```
