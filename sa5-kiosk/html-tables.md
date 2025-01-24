# Inactivity Timer 🧪

When in kiosk mode, the inactivity timer watches for keyboard, mouse, and touch events.

Conceptual

* install on every page
* Watches for keyboard, mouse, and touch events&#x20;
* Redirects to a specified home page if there's no activity&#x20;





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



