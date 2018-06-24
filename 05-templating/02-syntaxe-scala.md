# Syntaxe Scala

## Variables

```scala

// Variables

var x = 12 // variable avec inférence de type

val y = 5 // constante avec inférence de type

var z: Double = 12 // précisions du type

```

## Import

```scala

// Import

// _ équivalent à * en Java
import scala.collection._

// Import d'une classe
import scala.collection.Vector 

// Import sélectif
import scala.collection.{Vector, Sequence}

// Import renommé
import scala.collection.{Vector => Vec28}	renaming import.
```

## Structure de données

```scala

// Structure de données

// Création d'une liste de 3 éléments
val xs = List(1,2,3)
xs(2) // accès via un index

// Génériques
List[String] // équivalent Java List<String>

// Rangée
1 to 5
1 until 6 
1 to 10 by 2

```

## Structure de contrôle

```scala

// Structure de contrôle

// if
if (check) happy else sad

// for
for (x <- xs) {
  ...
}

for (i <- 1 to 5) {
  println(i)
}

```

## Classes

```scala

// Classes

// Créer une classe - paramètres privés
class C(x: R)
class C(private val x: R)

// Créer un objet
var c = new C(4)

// Classe abstraite
abstract class D { ... }

// Héritage
class C extends D { ... }
```

## Singleton

```scala

// Singleton

object Foo {
  var y = 5

  // permet d'exposer le singleton comme une fonction
  def apply (x: Int) = x + y 
}

// exécution de la méthode apply() 
Foo (1) 

List(1,2,3) // équivalent à List.apply(1,2,3)
```

## Fonctions

```scala

// Fonctions

// Utilisation du mot clé def
// la dernière instruction vaut le retour de la fonction

def f(x: Int) = { 
  x*x 
} 

// Une fonction Scala (syntaxe proche des expressions lambda Java 8)
(x:Int) => x + 1
val f = (x:Int) => x + 1

```

## Caractère `_`

```scala

// Caractère _

(1 to 5).map(_*2)

// équivalent à

(1 to 5).map( x => x*2)
```

## Currying

```scala

// Currying

object CurryTest extends App {
  def filter(xs: List[Int], p: Int => Boolean): List[Int] = ...

  def modN(n: Int)(x: Int) = ((x % n) == 0)

  // modN(2) = (x: Int) => ((x % 2) == 0)

  val nums = List(1, 2, 3, 4, 5, 6, 7, 8)

  println(filter(nums, modN(2))) // List(2,4,6,8)

  println(filter(nums, modN(3))) // List(3,6)
}

```
