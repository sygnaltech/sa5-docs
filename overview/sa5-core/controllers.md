# Controllers

**SA5 Controllers** are module-specific access points that are exposed to custom code.&#x20;

These are automatically installed when a library is used, and are available on the Window object, beneath `sa5.controllers`.

## Examples&#x20;

### Modals&#x20;

When SA5 Modals in installed `sa5.controllers.modals` is available and can be used to display a specific named modal;&#x20;

```html
<script>
sa5.controllers.modals.display("modal1", true); 
</script>
```





