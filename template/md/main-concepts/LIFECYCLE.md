---?
### Lifecyle
(Before using React Hooks)

![TIP](template/img/lifecycle.jpg)

+++?
@snap[north]
[deprecated]componentWillMount
@snapend

@snap[west]
componentWillMount не особо отличается от конструктора и вызывается лишь раз в изначальном жизненном цикле.
@snapend

@snap[south-west span-45]
<br>
Можно делать: 
@ul[](false)
- Устанавливать изначальное состояние компонента.
@ulend
@snapend

@snap[south-east span-45]
<br>
Лучше не делать: 
@ul[](false)
- Не выполнять никаких сайд-эффектов.
@ulend
@snapend
