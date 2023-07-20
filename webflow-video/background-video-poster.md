# Background Video Poster ❺

In HTML, a [video poster](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-poster) refers to an image that should be shown while the video is downloading.

```
<video poster="URL">
```

On background videos, this image is specified in the `data-poster-url` attribute, and Webflow generates a thumbnail image for you automatically.

In some cases, you may prefer to create your own image, or to create a WEBP image as recommended by Google Lighthouse. This feature allows you to specify your own.

**Note:** Standard `<video>` elements can also specify a video poster, using the `poster` attribute- however in Webflow, the standard video elements are designed to embed video players such as YouTube’s which use an `<iframe>` embed approach instead.

## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

This tool will replace the `data-poster-url` attribute on Webflow’s background videos with the image url you specify.

To use-

* Create and setup your background video element
* Create your poster image, e.g. a WEBP file, and add it to your website assets
* Get the URL of that uploaded asset
* Select your video element, and add a custom attribute of `wfu-data-poster-url`, and a value of your poster’s URL

Add the WFU video library to your page or site just before the closing body element.

On page load, WFU will find your background videos with that special attribute, and apply your specified URL value to the `data-poster-url`.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this feature, so we’ll use a _no-code_ integration approach.

Install JS in **HEAD**, generally site-wide.

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Video -->
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@v5.1.1/dist/nocode/webflow-video.min.js"></script>
```
{% endcode %}

### STEP 2 - Apply `wfu-data-poster-url` to the Background Videos <a href="#step-2---apply-wfu-data-poster-url-to-the-background-videos" id="step-2---apply-wfu-data-poster-url-to-the-background-videos"></a>

See above for details.

\
