---
description: Download file assets like PDFs or images, rather than displaying them
---

# Download File

<img src="../.gitbook/assets/file.excalidraw (8).svg" alt="" class="gitbook-drawing">

## Goals

* Download a file rather than displaying it&#x20;
* Work with Webflow's hosting CDN, which is cross-domain and does not support CORS &#x20;
* Support a custom filename&#x20;
* Work with both asset-stored files, and CMS-stored &#x20;

## Use Cases&#x20;

* Download a PDF, rather than displaying it&#x20;
* Download an image&#x20;

## Demonstration

<table data-view="cards"><thead><tr><th></th><th data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td>Demonstration Page</td><td><a href="https://sa5-html.webflow.io/file-download">https://sa5-html.webflow.io/file-download</a></td><td><a href="../.gitbook/assets/Frame 2.png">Frame 2.png</a></td></tr><tr><td>Cloneable</td><td><a href="https://webflow.com/made-in-webflow/website/sa5-html">https://webflow.com/made-in-webflow/website/sa5-html</a></td><td><a href="../.gitbook/assets/Frame 1.png">Frame 1.png</a></td></tr></tbody></table>

## Getting Started  <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).&#x20;

### Create your Button in Webflow <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

* Configure it to File download&#x20;
* Attach to your asset, or CMS file field, depending on your desired setup&#x20;

### Apply `wfu-download-file` to the HTML Embed element you want to decode <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

See above for details.

## Usage Notes&#x20;

wfu-download-file = ( filename )&#x20;

**Required.**&#x20;





## Technical Notes&#x20;



## Future&#x20;

? Test with multi-image fields&#x20;

? Use alt text as filename&#x20;

? Download button in image gallery &#x20;

? Test with components&#x20;

