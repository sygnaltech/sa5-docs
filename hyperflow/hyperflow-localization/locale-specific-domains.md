---
description: Use locale-specific domains and subdomains with your Webflow localized site.
---

# Locale-Specific Domains



Locale-Specific Domains & Sub-Domains

[https://discourse.webflow.com/t/seperate-domains-for-localisations/262898/4](https://discourse.webflow.com/t/seperate-domains-for-localisations/262898/4)

## Path fixes

CMS paths are always

* Determine current locale, and whether it's an alt locale&#x20;

Fix paths so that they are e.g. `/blog` and not `/fr/blog` on the `domain.fr` custom domain.&#x20;



## Language Link cross-references



Rel="alternate" Links

Adjust these to the domain per locale





Splitting Sitemaps by Locale

Research these;

It appears that for rel="alternate" links in the sitemap, you can reference a different domain legitimately;&#x20;

```xml
<!-- Sitemap for example.com -->
<url>
  <loc>https://www.example.com/page1</loc>
  <xhtml:link 
     rel="alternate" 
     hreflang="fr" 
     href="https://www.example.fr/page1" />
</url>

<!-- Sitemap for example.fr -->
<url>
  <loc>https://www.example.fr/page1</loc>
  <xhtml:link 
     rel="alternate" 
     hreflang="en" 
     href="https://www.example.com/page1" />
</url>
```

Locale Switcher





Locale Map

FR -> `domain.fr`

EN -> `domain.en`

Other

Auto language detection and routing?

No, because domain already is locale-specific and will have locale-specific SEO.&#x20;

Cookie to handle preferred locale?&#x20;

