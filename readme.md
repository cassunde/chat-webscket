#Chat Simple - Using websocket

this simple project show how use websocket

**Obs:** the websocket server is the [api-jersey](https://github.com/cassunde/api-jersey)

Today's top browsers already support websocket, with very simple code:

- **Get started**

```
	var websocket = new WebSocket("ws://localhost:8080/api-jersey/chat");
```

-	**To open connection**

```
websocket.onopen = function() {
	log("Conected !!!");
};
```

-	**To close connection**

```
websocket.onclose = function() {
	alert("desconnected");
};
```

-	**To error**

```
websocket.onerror = function() {
	log("an error has occurred");
};
```

-	**To receive messages**

```
websocket.onmessage = function(data) {                
	var message = "<p>" + data.data + "</p>";
	var messageArea = document.getElementById("messageArea");
	messageArea.innerHTML += message;
	messageArea.scrollTop = messageArea.scrollHeight;
};
```

-	**to send message**

```
function sendMessage(msg) {
	log("Enviar mensagem (" + msg + ")");
	websocket.send(msg);
}            
```

this is a feature power, our applications not need use `setTimeout`
