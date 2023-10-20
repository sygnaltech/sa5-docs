---
description: What we're planning for SA5
---

# Future - Date formatting

Currently SA5 supports momentjs. It's already used by Webflow for date formatting and it offers a wide range of date formatting capabilities.

{% embed url="https://momentjs.com/docs/#/displaying/format/" %}

The reason this feature requires you to specify a format handler is that it's likely we'll add other handlers in the future such as Luxon, which have different formatting string capabilities.&#x20;

## Date Features

Moment offers some pretty great features that we may extend into attributes, such as;

* Relative time, e.g. time until and time since displays, e.g. "7 days until..." or "Published 23 days ago".&#x20;
* Locale support. We'll wait to see how Webflow's localization features shape up.&#x20;
* Calendar time

## Luxon

Offers a different range of formatting strings and options.&#x20;

[https://moment.github.io/luxon/#/install](https://moment.github.io/luxon/#/install)

[https://moment.github.io/luxon/#/formatting?id=table-of-tokens](https://moment.github.io/luxon/#/formatting?id=table-of-tokens)
