# Viewport META



## Goals

Give the ability to configure the viewport META, including

* width
* initial-scale
* minimum-scale
* maximum-scale
* user-scalable

and more.&#x20;

## Configuration Notes

In initial testing this revised viewport META seems to work well with modern iPhones ( early 2024 ). It seems to prevent scaling issues in how the phone shrinks or crops the webpage.&#x20;

{% code overflow="wrap" %}
```html
<meta content="width=device-width, initial-scale=1.0, minimum-scale=1.0" name="viewport" />
```
{% endcode %}



