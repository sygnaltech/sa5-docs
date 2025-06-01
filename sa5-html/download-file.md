---
description: Download file assets like PDFs or images, rather than displaying them
---

# Download File ❺

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

### Create your Link or Button in Webflow <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

* Configure the link as a File link &#x20;
* Reference your asset, or bind it to a CMS file field, depending on your desired setup&#x20;

### Apply Attributes to the Button element  <a href="#step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode" id="step-2---apply-wfu-decode-to-the-html-embed-element-you-want-to-decode"></a>

_See below for details._&#x20;

## Usage Notes&#x20;

### wfu-download-file = ( _filename_ )&#x20;

**Required.** Set the value to the clean filename you want the file downloaded as.&#x20;

{% hint style="success" %}
You can specify this as a literal value, or bind the attribute's value to a CMS text field that contains your desired filename.&#x20;
{% endhint %}

{% hint style="info" %}
If you filename specifies an extension, it will be used automatically.  If it does not specify an extension, then most browsers will automatically add the extension depending on the file type you are downloading.&#x20;
{% endhint %}

## Technical Notes&#x20;

Uses a blob approach to sidestep issues regarding Webflow's cross-domain assets CDN setup, lack of support for custom MIME encoding, and browser CORS restrictions relating to the `download` attribute.&#x20;

## Testing Notes

|          | Windows      | iOS  | Android      |
| -------- | ------------ | ---- | ------------ |
| Chrome   | 2025-Jun-01  |      | 2025-Jun-01  |
| Edge     | 2025-Jun-01  |      |              |
| Safari   | n/a          |      | n/a          |
| Firefox  |              |      |              |

## Future&#x20;

? Test with multi-image fields&#x20;

? Use alt text as filename&#x20;

? Download button in image gallery &#x20;

? Test with components&#x20;

## Credits&#x20;

Shout out to Matt Evans and Eric R for discussions that led to the addition of this solution to SA5.&#x20;

