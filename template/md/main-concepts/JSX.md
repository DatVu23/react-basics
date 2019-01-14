---?
### JSX

+++?
@snap[west text-italic span-60]
По существу, JSX просто предоставляет синтаксический сахар для функции React.createElement(component, props, ...children). JSX-код:
@snaped

@snap[south-west span-60]
```
  <div className="my-class" />
```

Компилируется в:

```
  React.createElement(
    'div',
    {className: 'my-class'},
    null
  )
```
@snaped

  
