# Play! Enhancer
Play! Enhancer est un plugin SBT qui permet :

* de générer des getters/setters des champs publiques d'une classe;

* réécrire le code pour remplacer l'utilisation des champs publiques par les getters/setters.

Activer le plugin :

```scala
addSbtPlugin("com.typesafe.sbt" % "sbt-play-enhancer" % "1.1.0")
```

Le plugin prends en compte uniquement les champs ayant les caractéristiques suivantes :

* public
* non statique
* non final
* dont les getters/setters ne sont pas redéfinis


```java

public class Person {
  public Long id;
  public String lastname;

  public String getLastname() {
    return this.lastname.toUpperCase();
  }
}

// Dans une autre classe
Person p = new Person();
p.id = 12; // sera transformé en p.setId(12)
System.out.println(p.id); // => System.out.println(p.getId())

System.out.println(p.lastname); // => le getter n'est pas invoqué
```

> ATTENTION : les IDEs ayant généralement leurs propres processus de compilation, il peut avoir des problématiques de prise en compte par les IDEs.
