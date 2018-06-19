# Play! et HTTP

Play! a été conçu pour inciter les développeurs à respecter la sémantique du protocole HTTP.

Pour traiter une requête HTTP, Play! met à disposition :

* Un fichier de configuration des routes (`conf/routes`) qui fait le lien entre une requête HTTP et une méthode Java.
  * Le développeur est invité à prendre des décisions sur le design de son API.

* Des contrôleurs dont les méthodes permettent de traiter une requête et générer une réponse.
  * Le développeur est invité à définir un code retour de la réponse HTTP.
