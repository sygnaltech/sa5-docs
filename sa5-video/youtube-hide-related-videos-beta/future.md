---
description: Future ideas for the YouTube hide related video feature
---

# Future

## Fix race condition, or render issue

* Ensure the YouTube Iframe API is loaded and ready before use.&#x20;
  * Poss setInterval or setTimeout as a test.&#x20;
* Async timing issues.&#x20;
* Rendering- logging may be triggering the browser's rendering engine to update the view.&#x20;

## Panel overlay

Consider a redesign that support some form of panel-based overlay&#x20;

* In-designer content support
* In-designer styling support
* CMS content-binding support&#x20;
* Allows different styling per-video&#x20;

This design would likely include a separate DIV with an named overlay tag, and the ability to-&#x20;

* Specify overlays per-video, or to use a default unnamed one&#x20;
* Specify different overlays for pause v. stop&#x20;
* Possibly include player and video info, title, current time, duration, etc &#x20;

## Other ideas&#x20;

* Consider support for lightbox videos&#x20;
  * [https://discourse.webflow.com/t/youtube-video-inside-a-lightbox-how-to-hide-the-youtube-recommendations/213926/4](https://discourse.webflow.com/t/youtube-video-inside-a-lightbox-how-to-hide-the-youtube-recommendations/213926/4)
* Consider support for **Webflow's Video** element&#x20;





