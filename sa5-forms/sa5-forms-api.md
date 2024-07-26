---
description: For advanced forms manipulations
---

# SA5 Forms API

{% hint style="info" %}
Our devs favor _TypeScript_, and class-centric encapsulated design. The examples here are written as such. If you are using vanilla JavaScript, adjust the code syntax to your needs.
{% endhint %}

## Controlling Form State

Setup the SA5 form object, to point to a named form;&#x20;

{% code overflow="wrap" %}
```typescript
let form: any; 
const formElem: HTMLElement | null = document.querySelector<HTMLElement>("[wfu-form='your-form-name']"); 
if(formElem)
   form = new sa5.Sa5Form(formElem); 
```
{% endcode %}

Set the form mode;

```typescript
this.form.setMode(0); // 0 = Active | 1 = Success | 2 = Error
```







## Typescript Definition

For devs using Typescript, you can declare SA5 Forms simply with;&#x20;

```typescript
declare namespace sa5 {

    enum WebflowFormMode {
        Active,
        Success,
        Error,
    }

    class Sa5Form {

        constructor(element: HTMLElement);

        setMode(mode: WebflowFormMode): void; 

    }

}
```

If you're using vanilla JavaScript, you do not need a declaration and can work with;

```javascript
window.sa5.Sa5Form
```

