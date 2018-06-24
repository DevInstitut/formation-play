# TP #3 - HTTP

## Model InboxItem

* Créer une classe `models.InboxItem` avec les champs privés suivants (penser à générer les getters/setters) :
 
 * id (java.util.UUID)
 * title (String)
 * url (String)
 * note (String)
 

* Ajouter un constructeur par défaut.

* Ajouter un constructeur avec les paramètres `title, url, note`.

* Redéfinir la méthode `toString()` pour qu'elle affiche les valeurs des champs.


## Interface InboxItemService

* Créer une interface `services.inbox.InboxItemService` avec les méthodes suivantes :

```java
public interface InboxItemService {

  List<InboxItem> findAll();
  Optional<InboxItem> findOne(UUID id);
  InboxItem save(String title, String url, String note);
  InboxItem update(UUID id, String title, String url, String note);
  Optional<InboxItem> delete(UUID id);
}
```

Cette interface modélise les accès aux données `InboxItem`.


## Implémentation `InboxItemServiceHashMap`

* Créer une classe `services.inbox.InboxItemServiceHashMap` qui implémente l'interface `InboxItemService`.

* Cette implémentation consiste à stocker les données en mémoire via la structure `java.util.HashMap<UUID,InboxItem>`.

* Pour l'implémentation de la méthode `InboxItem save(String title, String url, String note)`, générer un identifiant unique.
Par exemple, via la classe `java.util.UUID`.


## Contrôleur `InboxApiController`

* Créer une classe `controllers.api.InboxApiController` qui va gérer les accès à la ressource `/api/inbox`.

* Etendre `play.mvc.Controller`.

* Importer le service `InboxItemService` :

```java

public class InboxApiController extends Controller {


  private InboxItemService inboxItemService = new InboxItemServiceHashMap();


}
```

## API `text/plain`

### GET /api/inbox

* Implémenter l'API `GET /api/inbox` qui produit une réponse HTTP avec le code 200 et comme contenu la liste des objets `InboxItem` sous la forme d'une chaîne de caractères.

* Implémenter l'API `GET /api/inbox/[ID]` qui produit une réponse HTTP avec le code 200 et comme contenu l'objet `InboxItem` dont l'identifiant est fourni. Si l'identifiant n'est pas connu retourner un code 404.

* Pour tester vous pouvez utiliser le plugin Chrome Postman (https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop).

### POST /api/inbox

* Implémenter l'API `POST /api/inbox` avec les caractéristiques suivantes :
    * Trois informations sont attendues dans la requête HTTP : `title`, `url` et `note`.
    * Les données sont envoyées dans le format `application/x-www-form-urlencoded` dans le corps de la requête HTTP.
    * Si une des informations (`title`, `url` et `note`) est manquante, renvoyer une réponse avec le code 400 et le texte `les champs title, url et note sont tous obligatoires.`.
    * Dans le cas où la sauvegarde s'est bien déroulée, renvoyer une réponse avec le code 201 et l'objet InboxItem sous la forme d'une chaîne de caractères.

### DELETE /api/inbox/[ID]

* Implémenter l'API `DELETE /api/inbox/[ID]` avec les caractéristiques suivantes :
    * Si l'identifiant fourni n'est pas valide, renvoyer une réponse avec le code 404.
    * Si la suppression s'est bien déroulée, renvoyer un code 200.

### PUT /api/inbox/[ID] (optionnel)

* Implémenter l'API `PUT /api/inbox/[ID]` en s'inspirant des règles de l'API `POST /api/inbox`.

## API JSON (Négociation de contenu)

Nous souhaitons à présent gérer différents formats de données :
* Ajouter le support du format JSON
* Conserver le fonctionnement initial avec le format `text/plain`
* Avertir l'utilisateur quand un format n'est pas supporté.

 
* Modifier l'API  `GET /api/inbox` pour qu'il renvoie les données sous différentes formes suivant la valeur de l'entête `Accept` :
    * Si `Accept` contient `application/json`, renvoyer du JSON
    * Si `Accept` contient `text/plain`, renvoyer du texte.
    * Sinon envoyer un message d'erreur `Format xxxx non géré`.

* Modifier l'API `POST /api/inbox` pour accepte désormais des requêtes dont les données sont envoyées au format JSON (entête `Content-Type` : `application/json`).
En cas de succès, les données renvoyées peuvent être au format `JSON` ou `text/plain` suivant l'entête de requête `Accept`.


