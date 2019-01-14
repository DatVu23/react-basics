---?
### JSX

+++?
@snap[west text-italic span-60]
По существу, JSX просто предоставляет синтаксический сахар для функции React.createElement(component, props, ...children). JSX-код:
@snaped

```
  <div className="my-class" />
```
@snap[east]
Компилируется в:
@snaped
```
  React.createElement(
    'div',
    {className: 'my-class'},
    null
  )
```

  
