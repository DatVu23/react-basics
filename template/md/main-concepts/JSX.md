---?
### JSX

+++?
@snap[north-west span-60]
@size[0.7em](`По существу, JSX просто предоставляет синтаксический сахар для функции React.createElement(component, props, ...children0). JSX-код:`)
@snaped

@snap[south-east]
```
  <div className="my-class" />
```
@size[0.8em](Компилируется в:)
```
  React.createElement(
    'div',
    {className: 'my-class'},
    null
  )
```
@snaped


  
