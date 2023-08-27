---
description: Remember the state of a checkbox as the user changes pages
---

# Track checkbox state

## Overview

Remember whether a checkbox is clicked or not, and maintain that state on each page load as the user navigates through your site.

_Good for, e.g. a day/night mode switch._&#x20;

## Implementing

Place this in your SITE-wide /BODY custom code area;

{% code overflow="wrap" %}
```javascript
<script>
// Handle checkbox tracking
// both checked and unchecked events 
$("input[type='checkbox'][wfu-bind-tracked]").change(function() {
  const label = $(this).attr("wfu-bind-tracked");
  if(this.checked) 
    window.tracker.track(label);
  else
    window.tracker.untrack(label);
  updateTracked();
}); 
</script>
```
{% endcode %}

Also place this code _inside_ and _at the end of_ the `updateTracked()` function in your site-wide /BODY custom code.&#x20;

```javascript

  // Look for any data-bound checkboxes
  // and updated them according to the tracked state
  $("input[type='checkbox'][wfu-bind-tracked]").each(function() {
    const t = $(this).attr("wfu-bind-tracked");
    const checked = window.tracker.isTracked(t) || false; 
    
    // jQuery set checkbox checked
    // https://stackoverflow.com/a/19630917
    $(this).prop('checked', checked);
    
    // For custom-styled Webflow checkboxes
    // we must manually update the checked class state 
    const $customCheck = $(this).prev(); 
    const isCustomCheck = $customCheck.length === 1;
    if (isCustomCheck) {
      if (checked)
        $customCheck.addClass("w--redirected-checked"); 
      else
        $customCheck.removeClass("w--redirected-checked"); 
    }

  });
```
