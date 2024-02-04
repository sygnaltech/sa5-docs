# Query Param Passthrough



## Getting Started ( LOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

First, **add the library** as detailed in [Quick Start](../sa5-user-accounts/quick-start.md).

### STEP 2 - Add your Configuration Callback

Add this script right after the library in your _site-wide_ **before HEAD** custom code.

## Configuration

```html
<!-- Sygnal Attributes 5 | Url | Config -->
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['urlConfig', 
  (config) => {
    config.passthrough = true;
//    config.passthroughConfig = {
  //    ignorePatterns: 
    //};
    config.passthroughConfig.ignorePatterns.push("ignore");
    config.fixupRelative = true;
    config.targetExternal = false;
    return config;
  }]); 
</script>
```

Configure the routing options to paths you prefer. In the example above, we've used `/u/new` and `/u/home`. Replace these with the URLs you want. If you do not want a special first-login route, you can remove that line.&#x20;
