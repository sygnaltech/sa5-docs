# Tabs API

{% hint style="warning" %}
Documentation in progress.&#x20;
{% endhint %}

## Initialization <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

Outside of callback events, you can also access the SA5 Tabs object by constructing one explicitly;

```javascript
const tabs = new sa5.WebflowTabs(
    $("[wfu-tabs=demo1]")[0]
); 
```

Once you have this, you can call its methods and properties;

## Properties <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

* `name` property returns the `[wfu-tab]` name, if one was set.
* `currentIndex` gets or sets the 0-based index of the current tab ( i.e. 5 tabs would be numbered 0, 1, 2, 3, 4 ).
* `currentNum` gets or sets the 1-based index of the current tab ( i.e. 5 tabs would be numbered 1, 2, 3, 4, 5 ).&#x20;

## Methods <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>

* `goToFirst()` navigates to the first tab
* `goToLast()` navigates to the last tab
* `goToPrev()` navigates to the prev tab
* `goToNext()` navigates to the next tab

See [Slider Code Examples](../slider/slider-code-examples.md) for more.&#x20;

## Events

To receive events from tab changes setup an SA5 callback with the `tabChanged` event. When called, it will contain the tabs object, and the index of the new tab ( 0-based ).&#x20;

If you have multiple tabs elements marked with \[wfu-tabs], you can assign a unique name, and access it through `tabs.name`, as in this example;&#x20;

```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['tabChanged', 
  (tabs, index) => {
    
    console.log("TAB CHANGED", tabs.name, tabs, index); 

    switch(tabs.name) {
      case "demo1": 
        // A tab was clicked in the Demo 1 tabs element
        // index indicates which tab was clicked ( 0-based )
        break;
      case "demo2": 
        // A tab was clicked in the Demo 2 tabs element
        // index indicates which tab was clicked ( 0-based )
        break;
    }

  }]); 
</script>
```

## Examples

For example;

```javascript
$("#btnFirst").click(function() {
  const tabs = new sa5.WebflowTabs(
    $("[wfu-tabs=demo1]")[0]
  ); 
  tabs.goToFirst();
})
```

These examples assume that;

* You have a Slider
* The Slider has a `wfu-slider` attribute with a value of `slider1`&#x20;
* You have the SA5 library installed&#x20;

## Navigating Tabs

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







