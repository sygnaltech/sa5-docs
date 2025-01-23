# Future



## Modes

Some window vars indicating current mode-

* Default
* Kiosk
* Display

### Default mode

Current user is in a standard browser/phone accessing the site.  Suppress all kiosk functionality.

### Kiosk mode&#x20;





### Display mode

Hands-off display mode

Goals;

* Highlight





|                   | Default mode                                             | Kiosk mode                                                                                                                                                                         | Display mode                                                                                                                                                                        |
| ----------------- | -------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                   | Standard access from a desktop browser, tablet, or phone | Interactive, on-site                                                                                                                                                               | Hands-free                                                                                                                                                                          |
| Use cases         | Normal website access and functionality                  | <ul><li>Booking, at a front desk</li><li>Enrollment at a doctors office, at reception </li></ul>                                                                                   | <ul><li>A screen in a doctor's waiting room</li><li>A kiosk, when it's asleep, like a screensaver type mode</li></ul>                                                               |
| Goals             |                                                          | <ul><li>Provide current product / service catalog to users in-store, easily</li><li>Support user info capture, enrollments, newsletter signups </li><li>Customer reivews</li></ul> | <ul><li>Screensaver - protect the kiosk from screen burn </li><li>Feature specials and new products</li><li>Play video content seamlessly, start to end, and then advance</li></ul> |
| Specific features |                                                          | <ul><li>Touch-only interaction support</li><li>On-screen keyboard </li></ul>                                                                                                       | <ul><li>Content queue</li><li>IFRAME controller?</li></ul>                                                                                                                          |







## Kiosk-Specific Styling



To investigate

* Is it possible to use Webflow's new variable modes here, and to trigger a certain set of variable styling?&#x20;
* Are there useful conventions around variable naming, like `kiosk-...` &#x20;



## Reverse Proxy

One intriguing approach is to use a reverse proxy to create the kiosk-specific view.

* It makes element-level conditional visibility comprehensive
* Everything can be delivered on e.g. `kiosk.mysite.com` &#x20;
* Other features can be considered, such as worker processes and application functionality&#x20;
* Security
  * IP-restriction can be applied to prevent others from viewing those pages&#x20;
  * Or less-secure User-agent based restrictions  &#x20;



## ECommerce&#x20;

To investigate;&#x20;

* What are the factors involved in performing a transaction at the kiosk
  * CC entry
  * Card swipe&#x20;
  * Others...&#x20;
    * RFID, like touching a watch&#x20;
    * QR scan payment like Alipay and other Chinese payment systems&#x20;













