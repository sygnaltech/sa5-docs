# Handlers

Handlers are User-defined event handlers that are defined in code, which provide custom behaviors attached to specific SA5 modules.&#x20;

An example is hotkey handler installation.  This block both registers a hotkey and defines the custom code to execute when the hotkey is pressed.&#x20;

```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['hotkeys', (hotkeyHandler) => {
  hotkeyHandler.register("f2", () => {
    console.log("f2 pressed");
  });
}]);
</script>
```

## Notes&#x20;

* Handlers are classed, e.g. `hotkeys` to identify the module. &#x20;
* Each module has different capabilities, and will define its own API details for handlers.&#x20;













