---?
### Lifecyle
(Before using React Hooks)

![TIP](template/img/lifecycle.jpg)

+++?
@snap[north]
Constructor
@snapend

@snap[west text-green span-30]
@box[bg-white text-green box-recomendations](Можно:#Устанавливать состояние компонента.)
@snapend

@snap[east text-orange span-40]
@box[bg-white text-orange box-recomendations](Лучше не делать:#Не выполнять никаких сайд-эффектов.)
@snapend


+++?
@snap[north]
[deprecated]componentWillMount
@snapend

@snap[west]
ComponentWillMount не особо отличается от конструктора и вызывается лишь раз в изначальном жизненном цикле.
@snapend

@snap[south-west text-green span-40]
@box[bg-white text-green box-recomendations](Можно:#Обновлять состояние через this.setState.)
@snapend

@snap[south-east text-orange span-40]
@box[bg-white text-orange box-recomendations](Лучше не делать:#Не выполнять никаких сайд-эффектов.)
@snapend


+++?
@snap[north]
[deprecated]componentWillReceiveProps(nextProps)
@snapend

@snap[west]
Этот метод будет вызываться при каждом апдейт жизненном цикле, который будет происходить при изменениях в props
@snapend

@snap[south-west text-green span-40]
Можно:
@ul[](false)
- Синхронизировать состояние (state) с props
@ulend
@snapend

@snap[south-east text-orange span-40]
Лучше не делать:
@ul[](false)
- Не выполнять никаких сайд-эффектов.
@ulend
@snapend


+++?
@snap[north-west]
shouldComponentUpdate(nextProps, nextState, nextContext)
@snapend

@snap[west]
@size[1.6rem](`Этот метод будет вызываться при каждом апдейт жизненном цикле, который будет происходить при изменениях в props`)
@snapend

@snap[south-west text-green span-45]
Можно:
@ul[](false)
- Использовать для оптимизации производительности компонента
@ulend
@snapend

@snap[south-east text-orange span-50]
Лучше не делать:
@ul[](false)
- Не выполнять никаких сайд-эффектов.
- Не вызывать this.setState
@ulend
@snapend


+++?
@snap[north-west]
[deprecated]componentWillUpdate(nextProps, nextState)
@snapend

@snap[west]
Эта функция в основном используется для того чтобы сделать синхронизацию между состоянием (state) и props в случае если часть состояния компонента базируется на каких-либо props.
@snapend

@snap[south-west text-green span-40]
Можно:
@ul[](false)
- Синхронизировать состояние (state) с props
@ulend
@snapend

@snap[south-east text-orange span-40]
Лучше не делать:
@ul[](false)
- Не выполнять никаких сайд-эффектов.
@ulend
@snapend


+++?
@snap[north-west]
СomponentDidUpdate(prevProps, prevState, prevContext)
@snapend

@snap[west]
Этот метод будет вызываться после того как отработала функция render, в каждом цикле перерисовки.
@snapend

@snap[south-west text-green span-40]
@box[bg-white text-green box-recomendations](Можно:#Выполнять сайд-эффекты)
@snapend

@snap[south-east text-orange span-55]
@box[bg-white text-orange box-recomendations](Лучше не делать:#Не вызывать this.setState т.к. это будет вызывать циклическую перерисовку)
@snapend


+++?
@snap[north-west]
componentDidCatch(errorString, errorInfo)
@snapend

@snap[west]
@size[1.4rem](`Дополнение в React 16 – этот метод жизненного цикла является особым, т.к. он позволяет реагировать на события, происходящие в дочернем компоненте, а конкретно на любые неперехваченные ошибки в любом из дочерних компонентов.`)
@snapend

@snap[south-west text-green span-40]
@box[bg-white text-green box-recomendations](Можно:#Выполнять сайд-эффекты)
@snapend

@snap[south-east text-orange span-40]
@box[bg-white text-orange box-recomendations](Лучше не делать:#Не вызывать this.setState т.к. это будет вызовет перерисовку.)
@snapend


+++?
@snap[north-west]
componentWillUnmount
@snapend

@snap[west]
Используйте эту функцию для «очистки» после компонента, если он использует таймеры (setTimeout, setInterval), открывает сокеты или производит любые операции, которые нуждаются в закрытии или удалении.
@snapend

@snap[south-west text-green span-40]
Можно:
@ul[](false)
- Удалять таймеры и листнеры.
@ulend
@snapend

@snap[south-east text-orange span-40]
Лучше не делать:
@ul[](false)
- Не вызывать this.setState.
@ulend
@snapend


+++?
@snap[north-west]
static getDerivedStateFromProps(nextProps, prevState)
@snapend

@snap[west]
@size[1.4rem](`Основная ответственность этой новой функции — это убедиться, что состояние (state) и props синхронизированы, когда это необходимо. Основной смысл — это замена componentWillRecieveProps.)`)
<br>
@size[1.4rem](`getDerivedStateFromProps – это статическая функция и поэтому не имеет доступа к this – вместо этого от вас ожидают, что вы вернете объект, который будет смержен в будущее состояние компонента (в точности как работа с setState!)`)

+++?
@snap[north]
getSnapshotBeforeUpdate(prevProps, prevState)
@snapend

@snap[west]
@size[1.4rem](`Этот метод вызывается в “pre-commit фазе”, прямо перед изменениями из VDOM, которые должны быть отображены в DOM`)
<br>
@size[1.4rem](`Можно использовать в основном, если вам нужно прочитать текущее состояние DOM.`) 
@snapend
