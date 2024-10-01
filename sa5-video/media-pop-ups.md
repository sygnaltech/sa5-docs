---
description: Play a video from any pop-up source.
---

# Media Pop-Ups 🧪



## Goals

* Easily create links _anywhere_ to pop-up media;
  * Images
  * Video
    * Direct link to MP4&#x20;
    * YouTube
    * Vimeo
  * Audio
  * IFRAMED content?&#x20;
* With no need to create a popup
* With no limitations on Webflow's pop-up media types
  * e.g. YouTube&#x20;
* Play MP4's directly on a hosted environment like Cloudflare R2&#x20;
* Support basic player features
  * Autoplay on click
  * Seek to position
* Autoclose on finish?&#x20;

Metrics;

* Video play stats&#x20;

## Use cases

* Drop a link anywhere, and link it directly to a video ( MP4, currently )







## Future

Expand recognized links to include;

* Other video file formats
* Image file formats
*

Styling;

* Made the default lightbox similar looking to Webflow's&#x20;
* Allow custom lightbox styling by replacing the elements&#x20;
* Site-wide configs `{ ... }` in site wide code&#x20;

`#!#start on links`&#x20;

Overlay SVG, plus color and transparency? fg color?&#x20;

`w-richtext a img`&#x20;

Consider;

* Groups support&#x20;
* Integration with WF's lightbox in some way

Media player controls;&#x20;

* Autoplay
* Start/pause&#x20;
* Ensure playing audio stops on close&#x20;

Special;&#x20;

* Only create player elements on click (?) as an option for cookie compliance &#x20;

## Usage Notes

v1-&#x20;

All links on the pag



## Status

* Functioning in Lux project &#x20;
* MP4 only&#x20;



