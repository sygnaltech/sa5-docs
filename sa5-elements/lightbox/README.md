---
description: Enhance Webflow's Lightbox Element
---

# Lightbox Element ❺

See the sub pages for details on how to implement;

* CMS captions in lightboxes
* CMS lightbox groups

## Future Ideas

### CMS Video lightboxes&#x20;

* Pull the thumbnail as the image
* Size it properly for the video

### A/V lightboxes

CMS-driven A/V Lightboxes, where A and V can be specifically ordered.&#x20;

Problems;

* CMS does not have a gallery capability for videos&#x20;
* Videos must be / should be pre-loaded&#x20;
* YouTube related videos problem&#x20;
* No lightbox thumbnail support for CMS video fields

Solutions;

* Poss use image gallery with alt text to point to video URL
* Poss use Plyr to control video appearance&#x20;
* Poss pull YT thumb as basis automatically&#x20;
*

### Lightbox replacer

Use WF designer to setup and create your lightboxes, then we unwire it and use a separate lightbox provider to solve for the missing functionality;

* Better combination of video & image content
* Captions on video & images&#x20;
* CMS groups&#x20;
* Wraparound, etc.&#x20;
