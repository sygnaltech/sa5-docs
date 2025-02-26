# SA5 Data JS API



### STEP 4 - ( Optional ) Add a callback that executes custom code once data is loaded <a href="#step-2---setup-your-zap-and-link-your-webflow-form" id="step-2---setup-your-zap-and-link-your-webflow-form"></a>







{% hint style="warning" %}
NOT YET RELEASED: Coming soon
{% endhint %}

```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['datastoreLoaded', 
  (ds) => {
    console.log("DATASTORE LOADED", ds); 
  }]); 
</script> 
```



&#x20;

