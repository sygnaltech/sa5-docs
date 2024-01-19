# Hyperflow Single Page Application (SPA)

In SPAs, the page does not reload fully on navigation. Instead, content is dynamically loaded and rendered on the client-side, usually through JavaScript. When a user clicks a navigation link, the SPA updates the content without a full page refresh, often using AJAX to fetch data and update the page's content. This results in a smoother user experience, as it avoids the flicker and delay of traditional page reloads. Popular frameworks for building SPAs include React, Angular, and Vue.js.

## Concept

Reverse-proxy a Webflow-hosted site

RP-SPA would deliver a pre-designed frame for the page content, consisting of a script reference, an empty HTML page, and possibly some scripts and a loader. &#x20;

`/_loader` contains a pre-loader image, logo, animation, etc. Very simple. `<body>` only?&#x20;

`/_rp-spa`

`/_scripts/_rp-spa` delivered by RP-SPA&#x20;

&#x20;The browser would then execute those scripts and use the URL path specified to retrieve the underlying content, which would be passed through a proxy-funnel;

`/_rp-spa/proxy` that gates the underlying content

## Notes

Ideally all config is in the Webflow site itself

May need to distinguish site-level code from page-level code with `<-- -->` comments, so RP-SPA can use them efficiently and parse them efficiently from the docs.&#x20;

Ideally site would operate and be testable withour RP-SPA, as a standard site.

Certain portions may be excluded from the load, in a `/_master` page template, e.g. audio players.&#x20;

Consider caching and performance as well.&#x20;

Consider transitions and easing options, via section tags?&#x20;

Pages need to work on direct request as well.&#x20;

SEO- avoid SPA delivery?&#x20;

## Technical Process

Page request happens to `/foo/bar`

RP-SPA retrieves template

RP-SPA retrieves `/foo/bar`

Streaming process(?) renders template, pulling content from retrieved page, using specific marker indicators.&#x20;

No DOM -> better suited to an Amazon setup with nodeJS?&#x20;







