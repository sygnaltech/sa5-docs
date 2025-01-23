# Kiosk Setup

There are many hardware profiles you can use.

In general they will consist of;&#x20;

* Small pc
* Touch screen
* Internet connection&#x20;

Plus optional keyboard and/or mouse.&#x20;

{% hint style="info" %}
It may help to think of your kiosk configuration as either a;

* Desktop Kiosk, which has a keyboard and mouse and is used in a desktop-like fashion, plus the addition of a touch screen.&#x20;
* Tablet Kiosk, which has no keyboard and mouse and relies entirely on touch.&#x20;
{% endhint %}



## Using Google Chrome as your Kiosk Platform

Google Chrome has a built in kiosk mode, which runs full screen, hides the URL bar, right click menu and other features.

It provides a solid base for a simple, low-cost kiosk platform.&#x20;

### How to Start Chrome in Kiosk Mode

{% hint style="info" %}
This is for a Windows-based kiosk, if your kiosk is Mac-based it should be similar.
{% endhint %}

To start Chrome in kiosk mode you want to specify 3 things on the command line;

* Kiosk mode, using the `--kiosk` parameter.&#x20;
* The kiosk homepage URL to start with&#x20;
* A kiosk-specific user agent so that SA5 can differentiate kiosk browser visits from regular browser visits.  We use a user agent of `KioskApp/1.0`&#x20;

When starting Chrome, that looks something like this;&#x20;

```
chrome.exe --kiosk https://www.mysite.com/kiosk --user-agent="KioskApp/1.0"
```

Or for your staging site while you're testing your kiosk;

```
chrome.exe --kiosk https://mysite.webflow.io/kiosk --user-agent="KioskApp/1.0"
```









On a Windows s















{% hint style="info" %}
Note, if Chrome is not in your environment path you may need to locate it and use the full path.  On a Windows system, the default installatio path is usually;

`"C:\Program Files\Google\Chrome\Application\chrome.exe"`
{% endhint %}



### Create a Desktop Shortcut

To easily start the kiosk mode, I recommend setting up a desktop shortcut using the full command above.  That way simply double-clicking it will launch your kiosk&#x20;



### Exiting the Kiosk

If you need to exit the kiosk and you have a keyboard attached, hit CTRL+F4. &#x20;





## Kiosk Setup&#x20;







