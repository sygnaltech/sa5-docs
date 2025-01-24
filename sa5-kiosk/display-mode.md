# Display Mode

Think of display mode as a hands-free "player" for your website.&#x20;

It's designed to showcase specific content that is entertaining and informative, specifically for the purpose of making your site useful;

* On displays in your retail shop / restaurant / clinic reception / front window display&#x20;
* On kiosks, when they're not in use&#x20;

Ideally, it...

* Delivers visual and audio content&#x20;
  * With the ability to mute overall, temporarily









## Playlists

The central mechanic for describing what you want shown is the playlist.&#x20;

{% hint style="info" %}
This is conceptual, and being ideated.&#x20;
{% endhint %}

This should be easily manageable in the project, so the best approach is likely a dedicated /playlist page or folder, which contains hidden pages that are publicly accessible but not in the sitemap.&#x20;

Those pages would then use static content, elements, and collection lists to describe the content you want played, using custom attributes.&#x20;

### Playlist Settings

* Name
* Ordering is linear, or random&#x20;

### Playlist Items

* A page link, e.g. /product/something&#x20;
  * Could possibly be an external link?&#x20;
* An image
* A video &#x20;

## Player Configuration

* Muted
* What playlist to play

## Other

* Mode switching
  * Automatically switch into player mode on a kiosk, when it's inactive&#x20;
  * Automatically switch into kiosk mode when the user interacts ( mouse, keyboard, etc. )&#x20;
* Alerts.  In some cases, it's nice to show an alert bar, like the remaining amount of time a special is on.  This could be handled on a player page itself, e.g. /player&#x20;
* Item transitions, pre-load an iframe and then slide it in?&#x20;

## Technical Notes





## Implementation&#x20;

Considering an `<iframe>` approach so that the player controller is always laoded and brings content inside. To some extent this simplifies certain playlist item types, like fullscreen video and images.&#x20;

IMPORTANT, it may not be possible to iframe some ecom pages.&#x20;

Preloading will be important to minimize page switching.&#x20;

Auto-detect any form of failed load

* non-200&#x20;
* network freeze, spinning wheel&#x20;





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









