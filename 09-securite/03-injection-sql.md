# Injection SQL

Les API fournit par Play! "échappe" les données des requêtes.

Si vous prenez la décision d'écrire vos requêtes SQL, éviter les concaténations de chaines de caractères.

```java

// si name vaut
String name =  "'john';drop table speakers;'";

// et que vous écrivez ceci ...
jpaApi.em().createQuery("select * from speakers where name=" + name);

// ... oops :(

```
