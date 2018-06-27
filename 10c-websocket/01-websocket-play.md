# WebSocket & Play!

**/!\ Attention l'API est en cours d'évolution et devrait changer dans les prochaines versions.**

Pour créer un WebSocket avec Play ! :

* Créer une route pour exposer une action

```
GET     /myws   controllers.MyController.index
```

* Créer une action qui renvoie un WebSocket

```
public LegacyWebSocket<String> index() {
	return ...
}
```
