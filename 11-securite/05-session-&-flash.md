# Session & Flash

Pour garder des données à travers différentes requêtes, Play! propose deux  mécanismes de stockage :

* **La Session**. Les données stockées y sont disponibles pendant la session de travail utilisateur (durée de vie de l’onglet du navigateur). Le cookie utilisé par Play! est signé avec une clé secrète (stockée côté serveur). Cela permet d’empêcher un client de modifier ce cookie.

* **Le Flash**. Les données stockées y sont disponibles uniquement lors de la prochaine requête. Le cookie n’est pas signé, donc modifiable côté client

**Les données Session et le Flash ne sont pas sauvegardées côté serveur mais plutôt côté client** dans un cookie. Plusieurs conséquences :

Seules les chaines de caractères peuvent par conséquent être stockées.

Ces mécanismes ne sont pas faits pour stocker de grande quantité de données, le cookie étant limité à 4KB.

