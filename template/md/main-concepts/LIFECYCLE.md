---?
### Lifecyle
(Before using React Hooks)

![TIP](template/img/lifecycle.jpg)

+++?
@snap[north]
[deprecated]componentWillMount
@snapend

@snap[west]
ComponentWillMount не особо отличается от конструктора и вызывается лишь раз в изначальном жизненном цикле.
@snapend

@snap[south-west text-green span-40]
@css[text-green fragment](Можно делать:)
@ul[](false)
- Устанавливать состояние компонента.
@ulend
@snapend

@snap[south-east span-40]
@css[text-red fragment](Лучше не делать:)
@ul[](false)
- Не выполнять никаких сайд-эффектов.
@ulend
@snapend
