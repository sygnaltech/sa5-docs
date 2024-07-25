# Advanced Slider Use



## Next Slide Suppression

You can setup an SA5 callback that determines whether or not to allow the Next button to advance the slider.&#x20;

_This is useful specifically for multi-step forms._&#x20;

```javascript
window.sa5.push(['slideNextRequest', 
  (slider, index) => 
    console.log("SLIDE NEXT REQUEST", slider.name, slider, index); 
    return false;
    }]); 
```



## Prev Slide Suppression

You can setup an SA5 callback that determines whether or not to allow the Next button to back-scroll the slider.&#x20;

_This is useful specifically for multi-step forms._&#x20;

```javascript
window.sa5.push(['slidePrevRequest', 
  (slider, index) => {
    console.log("SLIDE NEXT REQUEST", slider.name, slider, index); 
    return false;
    }]); 
```





