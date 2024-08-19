# Accordion API



## Initialization <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Outside of callback events, you can also access the SA5 Slider object by constructing one explicitly;

```javascript
const accordion = new sa5.Sa5Accordion(
    document.querySelector('[wfu-accordion=demo1]') // any properly-tagged element
);
```

Once you have this, you can call its methods and properties;

## Properties <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

* `name` property returns the `[wfu-accordion]` name, if one was set.
* `currentIndex` gets or sets the 0-based index of the current slide ( i.e. 5 slides would be numbered 0, 1, 2, 3, 4 ).
* `currentNum` gets or sets the 1-based index of the current slide ( i.e. 5 slides would be numbered 1, 2, 3, 4, 5 ).&#x20;

## Methods <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

* `goToFirst()` navigates to the first slide
* `goToLast()` navigates to the last slide
* `goToPrev()` navigates to the prev slide
* `goToNext()` navigates to the next slide

See [Slider Code Examples](../slider/slider-code-examples.md) for more.&#x20;



## Examples

These examples assume that;

* You have a Slider
* The Slider has a `wfu-slider` attribute with a value of `slider1`&#x20;
* You have the SA5 library installed&#x20;

## Navigating Slides

{% hint style="info" %}
Remember to wrap your code in `<script>` `</script>` tags.
{% endhint %}

First, setup the slider object-

```javascript
document.addEventListener('DOMContentLoaded', function() { 

  // Initialize SA5 Webflow Tabs
  accordionDemo = new sa5.Sa5Accordion(
    document.querySelector('[wfu-accordion=accordion1]')
  );
  
  // Perform any initial setup
  // e.g. select item #2
  accordionDemo.currentNum = 2;
  
  console.log(accordionDemo);
});
```

Setup any buttons or other triggers you want, to perform other navigations.&#x20;

For example, suppose we have a button with an ID of `buttonNext` and we want it to navigate to the next slide;

```javascript
// On button click, navigate to next slide 
document.querySelector('#buttonNext').addEventListener('click', function() {
  accordionDemo.goToNext();
});
```







