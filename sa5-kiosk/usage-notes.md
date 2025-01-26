# Usage Notes

* Add the kiosk library, as in quick start
* Add the configuration block&#x20;
* Configure
* Csutomize your kiosk setup&#x20;

## Configuring the Kiosk

_SA5's Kiosk configuration is centralized._ &#x20;

You can paste this into your site-wide code section immediately after the library references, and configure the paramaters the way you want.&#x20;

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



## Configuration Settings

|                 |                                                                                                     | Default         |
| --------------- | --------------------------------------------------------------------------------------------------- | --------------- |
| homePath        | Identifies the home page of the kiosk. This is where the kiosk will return to on inactivity reset.  | /kiosk          |
| userAgent       |                                                                                                     | KioskApp/1.0    |
| inactivityTimer | The amount of time                                                                                  | 180 ( seconds ) |























{% hint style="info" %}
Note, if Chrome is not in your environment path you may need to locate it and use the full path.  On a Windows system, the default installatio path is usually;

`"C:\Program Files\Google\Chrome\Application\chrome.exe"`
{% endhint %}



### Create a Desktop Shortcut

To easily start the kiosk mode, I recommend setting up a desktop shortcut using the full command above.  That way simply double-clicking it will launch your kiosk&#x20;



### Exiting the Kiosk

If you need to exit the kiosk and you have a keyboard attached, hit CTRL+F4. &#x20;





## Kiosk Setup&#x20;







