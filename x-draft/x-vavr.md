# Vavr

Vavr (anciennement appelé Javaslang) est une librairie Java 8+ fournissant des structures facilitant la programmation fonctionnelle.

## Pourquoi la programmation fonctionnelle
 
### Raison N°1 : les effets de bord

Une application Java classique possède plusieurs effets de bord :
* Mutation d'une variable
* Ecriture dans la console
* Ecriture dans un fichier de log
* Communication avec une base de données
* Lancement d'une exception
* ...

Exemple de méthode produisant un effet de bord :

```java

// la signature de la méthode n'indique pas qu'une exception pourrait être lancée.
public Integer diviser(Integer nombre1, Integer nombre2) {
    
    // déclenche une exception si nombre2 vaut 0
    return nombre1 / nombre2;
}
```

Pour l'utilisateur d'une telle méthode, il y a clairement une rupture du flux d'exécution.

La programmation fonctionnelle préconise d'utiliser une structure **expressive** avec un typage exprimant le fait que cette méthode peut produire une erreur.

Pour ce cas de figure, Vavr fournit la structure `Try`.

La méthode ci-dessus deviendrait :

```java

// la signature de la méthode indique deux cas de sortie possibles :
// = Success(resultat)
// = Failure(exception)
public Try<Integer> diviser(Integer nombre1, Integer nombre2) {
    
    // l'exception est interceptée par la structure
    return Try.of(() -> nombre1 / nombre2);
}
```

### Raison N°2 : Transparence référentielle

Une fonction ou une expression est dite `transparente référentielle` si son invocation peut être remplacée par une valeur sans affecter le fonctionnement du programme.

Pour une fonction, les mêmes entrées produisent TOUJOURS les mêmes sorties.

```java

// n'est pas transparente référentielle
Math.random();

// est transparente référentielle
Math.max(1,2);

```

> Une fonction est dite `pure` si toutes les expressions qui la compose sont référentielles transparentes. 

Vavr incite à l'écriture d'expression référentielle transparente.

### Raison N°3 : Penser en valeurs

Les valeurs les plus intéressantes sont les **immuables** :

* elles ne produisent pas d'effets de bord dans un contexte Multi-threads.
* leurs méthodes `equals` et `hashCode` sont stables dans le temps.
* elles n'ont pas besoin d'être clonées


## Structures de données

3 types de structure de données usuelles :
* Structure de données mutable
* Structure de données immuable
* Structure de données persistante 

Vavr fournit sa propre hierarchie de structures de données.
Le seul point commun avec les structures du JDK est l'utilisation de l'interface `Iterable`.

> Pourquoi ne pas avoir hérité des structures du JDK ? A cause des méthodes qui mutent ces structures.



## Structure de données fonctionnelle

Une structure de données fonctionnelle est :
* immuable
* persistante

Toutes ses méthodes sont `transparente référentielles`.

### Liste chaînée

Créer une liste avec Vavr.

```java

List<Integer> liste1 = List.of(1, 2, 3, 4);

```

