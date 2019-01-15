---?
### Lifecyle
(Before using React Hooks)

![TIP](template/img/lifecycle.jpg)

+++?
@snap[north]
Constructor
@snapend

@snap[west text-green span-40]
Можно:
@ul[](false)
- Устанавливать состояние компонента.
@ulend
@snapend

@snap[east text-orange span-40]
Лучше не делать:
@ul[](false)
- Не выполнять никаких сайд-эффектов.
@ulend
@snapend


+++?
@snap[north]
[deprecated]componentWillMount
@snapend

@snap[west]
ComponentWillMount не особо отличается от конструктора и вызывается лишь раз в изначальном жизненном цикле.
@snapend

@snap[south-west text-green span-40]
Можно:
@ul[](false)
- Обновлять состояние через this.setState.
@ulend
@snapend

@snap[south-east text-orange span-40]
Лучше не делать:
@ul[](false)
- Не выполнять никаких сайд-эффектов.
@ulend
@snapend


+++?
@snap[north]
[deprecated]componentWillReceiveProps(nextProps)
@snapend

@snap[west]
Эта функция будет вызываться при каждом апдейт жизненном цикле, который будет происходить при изменениях в props
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
@snap[north]
shouldComponentUpdate(nextProps, nextState, nextContext)
@snapend

@snap[west]
Эта функция будет вызываться при каждом апдейт жизненном цикле, который будет происходить при изменениях в props
@snapend

@snap[south-west text-green span-45]
Можно:
@ul[](false)
- Использовать для оптимизации производительности компонента
@ulend
@snapend

@snap[south-east text-orange span-55]
Лучше не делать:
@ul[](false)
- Не выполнять никаких сайд-эффектов.
- Не вызывать this.setState
@ulend
@snapend


+++?
@snap[north]
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
@snap[north]
componentDidUpdate(prevProps, prevState, prevContext)
@snapend

@snap[west]
Эта функция будет вызываться после того как отработала функция render, в каждом цикле перерисовки. Это означает, что вы можете быть уверены, что компонент и все его дочерние компоненты уже перерисовали себя. Эта функция является единственной функцией, что гарантировано будет вызвана только раз в каждом цикле перерисовки, поэтому любые сайд-эффекты рекомендуется выполнять именно здесь.
@snapend

@snap[south-west text-green span-40]
Можно:
@ul[](false)
- Выполнять сайд-эффекты
@ulend
@snapend

@snap[south-east text-orange span-40]
Лучше не делать:
@ul[](false)
- Не вызывать this.setState т.к. это будет вызывать циклическую перерисовку.
@ulend
@snapend


+++?
@snap[north]
componentDidCatch(errorString, errorInfo)
@snapend

@snap[west]
Дополнение в React 16 – этот метод жизненного цикла является особым, т.к. он позволяет реагировать на события, происходящие в дочернем компоненте, а конкретно на любые неперехваченные ошибки в любом из дочерних компонентов.
@snapend

@snap[south-west text-green span-40]
Можно:
@ul[](false)
- Выполнять сайд-эффекты
@ulend
@snapend

@snap[south-east text-orange span-40]
Лучше не делать:
@ul[](false)
- Не вызывать this.setState т.к. это будет вызовет перерисовку.
@ulend
@snapend


+++?
@snap[north]
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
@snap[north]
static getDerivedStateFromProps(nextProps, prevState)
@snapend

@snap[west]
Основная ответственность этой новой функции — это убедиться, что состояние (state) и props синхронизированы, когда это необходимо. Ее основной смысл — это замена componentWillRecieveProps.
<br>
getDerivedStateFromProps – это статическая функция и поэтому не имеет доступа к this – вместо этого от вас ожидают, что вы вернете объект, который будет смержен в будущее состояние компонента (в точности как работа с setState!)
<br>
Эта функция используется, когда компонент обновляется, но также и когда он монтируется, сразу после вызова конструктора, поэтому вам больше не нужно использовать конструктор если вы хотите установить начальное состояние компонента из props
@snapend

+++?
@snap[north]
getSnapshotBeforeUpdate(prevProps, prevState)
@snapend

@snap[west]
Этот метод вызывается в “pre-commit фазе”, прямо перед изменениями из VDOM, которые должны быть отображены в DOM
<br>
Ее можно использовать в основном, если вам нужно прочитать текущее состояние DOM. 
Например у вас есть приложение, в котором новые сообщения добавляются сверху экрана – если пользователь будет скроллить вниз, и добавится новое сообщение, экран будет «прыгать» и это сделает UI тяжелее в использовании. Добавлением getSnapshotBeforeUpdate вы сможете рассчитать текущее положение скролла и восстанавливать его через апдейт DOM-а.
@snapend
