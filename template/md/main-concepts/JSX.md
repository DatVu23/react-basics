---?
### JSX

+++?
@snap[north-west span-60]
По существу, JSX просто предоставляет синтаксический сахар для функции React.createElement(component, props, ...children). JSX-код:
@snaped

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


  
