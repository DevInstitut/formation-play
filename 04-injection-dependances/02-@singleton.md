# @Singleton

L'annotation `javax.inject.Singleton` permet d'avoir une instance unique pour toute la vie de l'application.

```java
@Singleton
public class PizzaCache {
    
    private List<Pizza> pizzas = new ArrayList<>();

    public void add(Pizza p) {
        pizzas.add(p);
    }

    public List<Pizza> get() {
        return new ArrayList<>(this.pizzas);
    }
}
```
