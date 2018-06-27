# WebSocket

WebSocket (WS) est un protocole de communication qui permet une communication **bi-directionnelle**.

Coté navigateur Internet, une API Javascript est mise à disposition.

Coté serveur, WS permet de proposer du push de depuis un serveur. L'utilisation de WS nécessite un serveur compatible.

```js
if(window.WebSocket) {
	
  var ws = new WebSocket("http://echo.websocket.org/");
  
  ws.onopen = function(evt) { ... }; 
  ws.onclose = function(evt) { ... }; 
  ws.onmessage = function(evt) { ... }; 
  ws.onerror = function(evt) { ... };

  ws.send("premier message via WebSocket");
}
```
