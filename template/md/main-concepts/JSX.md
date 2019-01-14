---?
### JSX

+++?
@snap[north-west text-italic text-10 span-60]
По существу, JSX просто предоставляет синтаксический сахар для функции React.createElement(component, props, ...children). JSX-код:
@snaped

@snap[south-east]
```
  <div className="my-class" />
```
@size[10](Компилируется в:)
```
  React.createElement(
    'div',
    {className: 'my-class'},
    null
  )
```
@snaped


  
