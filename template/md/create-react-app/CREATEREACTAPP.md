---?
@title[Create React App]
### Используйте Create React App

+++?
@title[Why should we use Create React App];
@snap[west span-60]
@size[1rem](Create React App — инструмент для быстрого старта React-приложений. Не нужно тратить время на настройку Webpack, Babel и других привычных инструментов. Они заранее настроены и спрятаны.)
@snaped

++?
@snap[west span-60]
@size[1rem](Create React App предоставляет CLI-интерфейс для создания приложений с базовой структурой, устанавливает все нужные зависимости и добавляет в package.json скрипты для запуска, тестов и сборки приложения..)
@snaped
```javascript
// Include http module.
var http = require("http");

// Create the server. Function passed as parameter
// is called on every request made.
http.createServer(function (request, response) {
  // Attach listener on end event.  This event is
  // called when client sent, awaiting response.
  request.on("end", function () {
    // Write headers to the response.
    // HTTP 200 status, Content-Type text/plain.
    response.writeHead(200, {
      'Content-Type': 'text/plain'
    });
    // Send data and end response.
    response.end('Hello HTTP!');
  });

// Listen on the 8080 port.
}).listen(8080);
```