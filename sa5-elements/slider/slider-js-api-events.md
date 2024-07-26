# Slider JS API Events



### Receiving Slide Changed Events

To receive events from tab changes setup an SA5 callback with the `slideChanged` event. When called, it will contain the slider object, and the index of the new slide ( 0-based ).&#x20;

If you have multiple sliders marked with \[wfu-slider], you can assign a unique name, and access it through `slider.name`, as in this example;&#x20;

```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['slideChanged', 
  (slider, index) => {
    
    console.log("SLIDE CHANGED", slider.name, slider, index); 

    switch(slider.name) {
      case "demo1": // Demo 1 slide changed

        break;
      case "demo2": // Demo 2 slide changed

        break;
    }

  }]); 
</script>
```

### Manipulating the Slider <a href="#wfu-lightbox-captions-attribute" id="wfu-lightbox-captions-attribute"></a>



{% code overflow="wrap" %}
```typescript
sa5.push(['slideNextRequest', 
  (slider: any, index: any) => {
    console.log("SLIDE NEXT REQUEST", slider.name, slider, index); 

    // Example usage:
    // This will fetch the 3rd slide from the slider with the custom attribute 'wfu-slider="quiz"'
    const slide = this.getSlideByPosition(index + 1);
    if (slide) {
        console.log('Slide found:', slide);

      return this.checkRadioSelection(slide); 

    } else {
        console.log('Slide not found.');
    }

    return (index < 6); 
  }]); 
sa5.push(['slidePrevRequest', 
  (slider: any, index: any) => {
    console.log("SLIDE PREV REQUEST", slider.name, slider, index); 
    return (index > 0); 
  }]); 
```
{% endcode %}



```
```









