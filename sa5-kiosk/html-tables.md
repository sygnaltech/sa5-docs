# Inactivity Timer

When in kiosk mode, the inactivity timer watches for keyboard, mouse, and touch events.

* Watches for keyboard, mouse, and touch events&#x20;
* Redirects to a specified home page if there's no activity&#x20;

## Usage Notes&#x20;

install on every page, generally best to put this site-wide before-/head custom code area.&#x20;

### inactivityTimer: (sec) &#x20;

Set the seconds of inactivity before the browser will auto redirect to the `homePath` .&#x20;

## Example&#x20;

```html
<script type="application/sa5+json">
{
  "@context": "https://attr.sygnal.com",
  "@type": "KioskConfig",
  "@version": "0.1",
  "homePath": "/kiosk", 
  "userAgent": "KioskApp/1.0", 
  "inactivityTimer": "180"  
}
</script>
```



