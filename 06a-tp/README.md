# TP #6 - Formulaires

## Créer une nouvelle tâche

* Ajouter un bouton `New` dans la page `Inbox`.

![](images/tp-05-btn-new.png)

* Implémenter le formulaire de création de nouvelle tâche.

![](images/tp-05-create-inbox-item.png)

2 routes sont à créer :

```
GET     /inbox/create
POST    /inbox/create 
```

* Ajouter des contraintes de validation sur le titre d'une tâche (champ `title`) : champs requis et de taille minimum égale à 3.

* Lors de la soumission du formulaire, en cas d'erreur de validation, la page courante s'affiche à nouveau.

* Lors de la soumission du formulaire, en cas de succès, l'utilisateur est redirigé vers la liste des tâches (`Inbox`).

## Editer une tâche

* Ajouter le bouton `Edit`.

![](images/tp-05-btn-edit.png)

* Implémenter le formulaire d'édition pour permettre la mise à jour d'une tâche.

![](images/tp-05-edit-inbox-item.png)

2 routes seront à créer :

```
GET     /inbox/edit/:id
POST    /inbox/edit/:id 
```

* Lors de la soumission du formulaire, en cas d'erreur de validation, la page courante s'affiche à nouveau.

* Lors de la soumission du formulaire, en cas de succès, l'utilisateur est redirigé vers la liste des tâches (`Inbox`).