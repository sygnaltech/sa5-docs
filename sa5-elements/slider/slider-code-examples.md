---
description: SA5 Slider Code Examples
---

# Slider JS API

### Manipulating the Slider <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Outside of callback events, you can also access the SA5 Slider object by constructing one explicitly;

```javascript
const slider = new sa5.WebflowSlider(
    document.querySelector('[wfu-slider=demo1]')
);
```

Once you have this, you can call its methods and properties;

Properties;

* `name` property returns the `[wfu-slider]` name, if one was set.
* `currentIndex` gets or sets the 0-based index of the current slide ( i.e. 5 slides would be numbered 0, 1, 2, 3, 4 ).
* `currentNum` gets or sets the 1-based index of the current slide ( i.e. 5 slides would be numbered 1, 2, 3, 4, 5 ).&#x20;

Methods;&#x20;

* `goToFirst()` navigates to the first slide
* `goToLast()` navigates to the last slide
* `goToPrev()` navigates to the prev slide
* `goToNext()` navigates to the next slide

See [Slider Code Examples](slider-code-examples.md) for more.&#x20;





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



