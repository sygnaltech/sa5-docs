# Breakpoints

Webflow offers 7 breakpoints.&#x20;

Some of SA5's attribute settings are breakpoint-aware, meaning that their configuration can be changed for specific breakpoints.&#x20;

On these attributes, that's achieved by adding a special suffix to the custom attribute name.  For example, an attribute named `sa-attr` could have these suffixes.&#x20;

{% hint style="info" %}
These attributes are applied in a cascading fashion in the same way that breakpoints work within Webflow directly. &#x20;
{% endhint %}







| Attribute + suffix | Covers                      |                 |
| ------------------ | --------------------------- | --------------- |
| `sa-attr:1920`     | 1920+ breakpoint            | 1920px+         |
| `sa-attr:1440`     | 1440 breakpoint             | 1440px+         |
| `sa-attr:1280`     | 1280 breakpoint             | 1280px+         |
| `sa-attr`          | Desktop ( base ) breakpoint | All breakpoints |
| `sa-attr:T`        | Tablet breakpoint           | up to 990px     |
| `sa-attr:L`        | Landscape breakpoint        |                 |
| `sa-attr:P`        | Portrait breakpoint         |                 |





sa-layout

sa-layout-target

sa-layout-pos = 5

sa-layout-pos:T = 4

sa-layout-pos:L = 3





Layout-sensitive elements

Re-execute on breakpoint changes&#x20;









