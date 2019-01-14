---?
### JSX

+++?
@snap[north-west span-60]
По существу, JSX просто предоставляет синтаксический сахар для функции React.createElement(component, props, ...children). JSX-код:
@snaped

@snap[south-east]
```
  <div className="my-class" />
```
@size[10em](Компилируется в:)
```
  React.createElement(
    'div',
    {className: 'my-class'},
    null
  )
```
@snaped


  
