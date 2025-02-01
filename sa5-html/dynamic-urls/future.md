# Future



## Supporting Other Elements&#x20;

Several HTML elements have attributes that reflect a URL. These attributes are commonly used for linking resources, navigation, media, and metadata. Here’s a list:

#### 🔗 **Anchor & Navigation Elements**

* `<a href="https://example.com">` → **`href`**: Specifies the hyperlink destination.
* `<area href="https://example.com">` → **`href`**: Defines a hyperlink in an image map.
* `<link href="https://example.com/style.css">` → **`href`**: Links external stylesheets, icons, etc.
* `<base href="https://example.com/">` → **`href`**: Sets the base URL for relative links on the page.

#### 🖼️ **Media Elements**

* `<img src="https://example.com/image.jpg">` → **`src`**: Defines the image source.
* `<audio src="https://example.com/audio.mp3">` → **`src`**: Specifies the audio file location.
* `<video src="https://example.com/video.mp4">` → **`src`**: Specifies the video file location.
* `<source src="https://example.com/media.mp4">` → **`src`**: Used within `<audio>` and `<video>` elements.
* `<track src="https://example.com/subtitles.vtt">` → **`src`**: Specifies caption files for media.

#### 🎬 **Embedded & Interactive Content**

* `<iframe src="https://example.com">` → **`src`**: Embeds another web page.
* `<embed src="https://example.com/animation.swf">` → **`src`**: Embeds external content (e.g., Flash, PDFs).
* `<object data="https://example.com/file.pdf">` → **`data`**: Specifies the URL of an external resource.

#### 📝 **Forms & Inputs**

* `<form action="https://example.com/submit">` → **`action`**: Specifies where to send form data.
* `<input type="image" src="https://example.com/button.png">` → **`src`**: Defines the image button source.

#### 📜 **Scripts & Styles**

* `<script src="https://example.com/script.js">` → **`src`**: Specifies the JavaScript file location.
* `<style>@import url("https://example.com/style.css");</style>` → **CSS `url()`** function (indirect reference).

#### 🧩 **Web Components & App-Specific**

* `<applet codebase="https://example.com/java/">` → **`codebase`**: Specifies the base URL for a Java applet (deprecated).
* `<meta content="https://example.com" property="og:url">` → **`content`** (in Open Graph meta tags).
* `<meta http-equiv="refresh" content="5; url=https://example.com">` → Redirects to a URL.



