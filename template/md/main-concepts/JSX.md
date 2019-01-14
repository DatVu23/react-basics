---?
### JSX

+++?
@snap[east span-60]
По существу, JSX просто предоставляет синтаксический сахар для функции React.createElement(component, props, ...children). JSX-код:
@snaped

```
  <div className="my-class" />
```

```
  React.createElement(
    'div',
    {className: 'my-class'},
    null
  )
```

  
