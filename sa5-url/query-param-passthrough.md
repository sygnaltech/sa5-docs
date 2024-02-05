---
description: >-
  Automatically pass through querystring params from the current page, as users
  navigate through your site.
---

# Query Param Passthrough ❺

{% hint style="info" %}
**BETA:** This library has just been released and has a lot of configuration options that have not been fully tested by our community.  Please report any issues in the forum, link above.
{% endhint %}

## Use Cases

* Pass UTM tracking params from the landing page, as the user navigates through the site. Capture them when the user submits a form.
  * See SA5's Data-binding features for no-code binding of [querystring params](../sa5-data/data-sources/url-query-params.md) to form inputs.&#x20;
* Pass referrer-tracking params in the same way&#x20;

## Configuration

This library has extensive configuration options.&#x20;

{% hint style="info" %}
All **SA5 Url** lib features are handled in a single `urlConfig` configuration block, however feature-specific configurations are represented as sub objects. Typically you can enable or disable a feature, and provide a custom configuration if you choose.
{% endhint %}

Here are the configuration options for Query param passthrough;&#x20;

```html
<!-- Sygnal Attributes 5 | Url | Config -->
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['urlConfig', 
  (config) => {
    config.passthrough = true;
    config.passthroughConfig = {
      ignorePatterns: ["ignore", /_page$/],
      overwriteExisting: true,
      internalOnly: false
    };
    return config;
  }]); 
</script>
```

### passthrough = true | false

_Defaults to false._

Enables or disables query param passthrough.

### passthroughConfig

Specifies query param passthrough config options.&#x20;

#### passthroughConfig.ignorePatterns

Defines which param keys to ignore, for example, this configuration will not pass through param keys of `ignore` or Webflow's pagination params like `j2l89skd_page`.&#x20;

```javascript
config.passthroughConfig = {
  ignorePatterns: ["ignore", /_page$/]
};
```

{% hint style="info" %}
You can have as many ignore patterns as you like, and can specify both literal strings and regex strings.
{% endhint %}

Defaults to  `[ /_page$/ ]`.&#x20;

Not thoroughly tested, but you should also be able to do add and remove operations like;&#x20;

```javascript
config.passthroughConfig.ignorePatterns.push("ignore");
```

#### passthroughConfig.overwriteExisting = true | false <a href="#getting-started-locode" id="getting-started-locode"></a>

If a link already has a param with this name, this setting determines whether a querystring param with the same name will overwrite it.&#x20;

Defaults to _false_.

#### passthroughConfig.internalOnly = true | false

Determines whether param passing targets internal links only, or external links as well.&#x20;

Defaults to _true_.

## Getting Started ( LOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](quick-start.md).

### STEP 2 - Add your Configuration Callback

Add this configuration section above right after the library in your **before HEAD** custom code. Typically this will be in the site-wide custom code configuration.&#x20;
