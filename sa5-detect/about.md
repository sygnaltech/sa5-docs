---
description: About the SA5 Detect Library
---

# 🔍 About SA5's Detect Lib

This this lib supports detection of your visitor characteristics, and actions based on them.

Initially we are focused on geo-detection using a GEOIP methodology.&#x20;

* Route users to specific pages depending on their location&#x20;

Coming soon;&#x20;

* Conditionally display elements depending on location &#x20;

## Future

User-agent detection, with accordant routing and conditional-vis;

* Language
* Device type
* Browser type
* etc.&#x20;

First time visitor detection.&#x20;

Referral detection.&#x20;

Onready callback&#x20;

Data binding&#x20;



### Detection Overrides

E.g. use case

dropdown showing countries

detected country selected&#x20;

changing forces a change on the country setting

_reloads page_ to reapply detect with override setting&#x20;



Explicit overrides on detected UserInfo, such as the country, city, browser type...&#x20;

Set by script,&#x20;

window.user-info-overrides&#x20;

set directly on overrides objects, via detect&#x20;

Saved data binds&#x20;

\>$detect.geo.country



Override Detects UserInfo?&#x20;

* Override country
* Override city
* Override language
* Override browser type

And remember - cache overrides?&#x20;







### Filter defaulting

Support for queries, like UserInfo load triggers, and the ability to e.g. trigger FS filters depending on those details automatically.&#x20;

Initialization only, once.&#x20;
