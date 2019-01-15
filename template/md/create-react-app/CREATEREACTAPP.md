---?
@title[Create React App]
### Используйте Create React App

+++?
@title[Why should we use Create React App];
@snap[west span-60]
@size[1rem](Create React App — инструмент для быстрого старта React-приложений. Не нужно тратить время на настройку Webpack, Babel и других привычных инструментов. Они заранее настроены и спрятаны.)
@snaped

+++?
@snap[west span-50]
@size[1rem](Create React App предоставляет CLI-интерфейс для создания приложений с базовой структурой, устанавливает все нужные зависимости и добавляет в package.json скрипты для запуска, тестов и сборки приложения..)
@snaped
<br>
```
npm install -g create-react-app
create-react-app my-app
cd my-app/
npm start # yarn start
```

+++?
@snap[north-west]
Причины использования Create React App
@snapend

@snap[west list-content-verbose span-100]
<br>
@ul[](false)
- В структуре приложения нет конфигурации и лишних файлов.
- Весь стек обновляется одной строкой.
- Стек разработки фиксированный и стабильный.
- Функциональность этого инструмента быстро расширяется.
- Удобная работа с CSS.
- React scripts.
@ulend
@snapend

@snap[south-west template-note text-gray]
@N причин, чтобы использовать Create React App
@snapend