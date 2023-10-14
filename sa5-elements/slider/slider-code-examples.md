---
description: SA5 Slider Code Examples
---

# Slider Code Examples

These examples assume that;

* You have a Slider
* The Slider has a `wfu-slider` attribute with a value of `slider1`&#x20;
* You have the SA5 library installed&#x20;

## Navigating Slides

Here we'll use jQuery as&#x20;

{% hint style="info" %}
Remember to wrap your code in `<script>` `</script>` tags.
{% endhint %}

First, setup the slider object-

```javascript
document.addEventListener('DOMContentLoaded', function() { 

  // Initialize SA5 Webflow Tabs
  sliderDemo = new sa5.WebflowSlider(
    document.querySelector('[wfu-slider=slider1]')
  );
  
  // Perform any initial setup
  // e.g. select slide #2
  sliderDemo.currentNum = 2;
  
  console.log(sliderDemo);
});
```

Setup any buttons or other triggers you want, to perform other navigations.&#x20;

For example, suppose we have a button with an ID of `buttonNext` and we want it to navigate to the next slide;

```javascript
// On button click, navigate to next slide 
document.querySelector('#buttonNext').addEventListener('click', function() {
  sliderDemo.goToNext();
});
```



