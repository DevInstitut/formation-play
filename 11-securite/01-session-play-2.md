# Session Play 2

La session permet d'éviter à un utilisateur de saisir ses informations de connexion à chaque requête HTTP.

La session Play 2 est **stockée dans un cookie** (donc côté client). 
Cette approche est différente celle choisie par Java EE (informations utilisateurs sauvegardées côté serveur).

Le choix du cookie implique des limitations :
* impossible de sérialiser de gros objets (maximum 4Ko et uniquement de la chaîne de caractères)
* les données de session sont consultables par le client. Il faut alors éviter de stocker des informations critiques.
* le client peuvent vider son cache et supprimer ses cookies quand il veut.


La session Play 2 n'est pas chiffrée mais signée avec une clé configurée dans le fichier `conf/application.conf` via la propriété `application.secret`.

```properties
application.secret="6uU34sXWd:vm/...19]6H4omJ0pvNgQOIw"
```

Cette clé doit rester secrète. Ne pas la commiter sur Github :)

