# Hyperflow Gitbook

## Features

### Add auto-nav-sync

When nav occurs;

* From direct URL, auto-sync the left nav to match the current page
* From search, auto-sync the left nav to match the current page
* From left nav, do nothing

### Vars

{gb{ kv key \}}

### CSS



## Technical Notes

### Determine nav mode to use&#x20;

### Adjust position

```json
document.querySelector('a[href="/overview/how-to-add-custom-code"]').scrollIntoView({
    behavior: 'smooth'
});
```



{% code overflow="wrap" %}
```json
const element = document.querySelector('a[href="/overview/how-to-add-custom-code"]');
if (element) {
    element.scrollIntoView(); // Scrolls to the element
    const scrolledY = window.scrollY;

    if(scrolledY){
        window.scroll(0, scrolledY - window.innerHeight / 2 + element.getBoundingClientRect().height / 2);
    }
}
```
{% endcode %}
