---
description: Conditionally hide/show elements depending on tracked state
---

# Conditional Element Visibility

Use SA5's custom attributes to tag elements for conditional visibility, depending on your tracked state.&#x20;

## Use Cases

Suppose a user clicks a special marketing link, and has landed on a special hidden landing page for that offer. You can track that they've been to that page, and then throughout your site, you can have some special reminders conditionally appear about the offer.&#x20;

Suppose a user completed sign-up to your great new class, and saw the thank you page. You can remember that and now, they're no longer bothered with ads and CTAs through your site telling them to enroll.&#x20;

## Implementing

Add this to your site-wide **before BODY**.&#x20;

Throughout your site, you can then identify the elements you want to be conditionally visible based on tracked or untracked state.&#x20;

{% hint style="info" %}
Everything you track has a unique identifier that you've assigned, and you can have any number of these.  For these examples, we'll pretend you have a tracker named `trackername`.
{% endhint %}

To display an element only when tracking is been set, assign this custom attribute to the element.

`wfu-show-tracked` = `trackername`&#x20;

To hide an element when tracking has been set, assign this custom attribute.&#x20;

`wfu-hide-tracked` = `trackername`

In your site-wide **before BODY** custom code, add this;&#x20;

{% code overflow="wrap" %}
```javascript
<script>
$(function() {
  
  // Update the UI to reflect current tracking state
  // especially controls, and conditional visibility 
  updateTracked();
  
});

// Refresh UI to show what is being tracked
// with the current tracker type 
function updateTracked() {

  // Show anything marked to show on tracked state
  $("[wfu-show-tracked]").each(function () {
    if(window.tracker.isTracked($(this).attr("wfu-show-tracked")))
      $(this).show();
    else
      $(this).hide();
  });
  
  // Hide anything marked to hide on tracked state
  $("[wfu-hide-tracked]").each(function () {
    if(!window.tracker.isTracked($(this).attr("wfu-hide-tracked")))
      $(this).show();
    else
      $(this).hide();
  });
    
  // PLACE ADDITIONAL CODE HERE
  // When directed to in the feature-specific instructions
    
}
</script>
```
{% endcode %}



