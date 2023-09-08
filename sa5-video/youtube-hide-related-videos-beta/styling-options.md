---
description: Styling the YouTube Norel overlay
---

# Styling Options



It is possible to change the styling of the overlay, using custom CSS.

You can;

* change the background color
* change the background texture
* change the image or icon used, including to reference it from an asset URL ( SVG is recommended, but not required ).&#x20;
  * possibly, scale it relative to the video size&#x20;

{% hint style="warning" %}
Due to the way this technique works and the use of the `::after` pseudo-class, there is no way to use the Designer for styling, and all of the style attributes MUST be included in the override as they do not carry through.&#x20;
{% endhint %}

Copy the following code and place it in your page or site head **immediately after** the SA5 video library and CSS references. &#x20;

{% code overflow="wrap" %}
```html
<style>
[wfu-youtube-norel].sa5-video-paused::after {
    content: "";
    position: absolute;
    top: 0; 
    left: 0;
    bottom: 0; 
    right: 0;
    cursor: pointer;
    background-color: blue;  /* Overridden */
    background-repeat: no-repeat;
    background-position: center;
    background-size: 40px 40px;
    background-image: url(data:image/svg+xml;utf8;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZlcnNpb249IjEiIHdpZHRoPSIxNzA2LjY2NyIgaGVpZ2h0PSIxNzA2LjY2NyIgdmlld0JveD0iMCAwIDEyODAgMTI4MCI+PHBhdGggZD0iTTE1Ny42MzUgMi45ODRMMTI2MC45NzkgNjQwIDE1Ny42MzUgMTI3Ny4wMTZ6IiBmaWxsPSIjZmZmIi8+PC9zdmc+); 
}
[wfu-youtube-norel].sa5-video-ended::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    cursor: pointer;
    background-color: blue;  /* Overridden */
    background-repeat: no-repeat;
    background-position: center;
    background-size: 64px 64px;
    background-image: url(data:image/svg+xml;utf8;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxMjgiIGhlaWdodD0iMTI4IiB2aWV3Qm94PSIwIDAgNTEwIDUxMCI+PHBhdGggZD0iTTI1NSAxMDJWMEwxMjcuNSAxMjcuNSAyNTUgMjU1VjE1M2M4NC4xNSAwIDE1MyA2OC44NSAxNTMgMTUzcy02OC44NSAxNTMtMTUzIDE1My0xNTMtNjguODUtMTUzLTE1M0g1MWMwIDExMi4yIDkxLjggMjA0IDIwNCAyMDRzMjA0LTkxLjggMjA0LTIwNC05MS44LTIwNC0yMDQtMjA0eiIgZmlsbD0iI0ZGRiIvPjwvc3ZnPg==);
}
</style> 
```
{% endcode %}

