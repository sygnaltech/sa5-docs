---
description: Here's what we're thinking...
---

# Using Access Groups for Conditional Visibility

At this point our discussions are focusing on two key use cases for Access Groups;

1. Conditional visibility of elements
2. Routing

## Modify Your Page by Access Group&#x20;

Currently, you can check for access-group inclusion by checking the array, e.g.;&#x20;

```javascript
user.access_groups.includes('pro');
```

{% hint style="info" %}
This technique is demonstrated in the [cloneable](https://webflow.com/made-in-webflow/website/current-user-info) to apply user access group info to attribute-tagged elements.
{% endhint %}

```html
<script> 
window.sa5.push(['userInfoChanged', 
  (user) => {
    
    // Check to see if access_groups info is loaded
    if(user.user_data_loaded.access_groups) {
    
      // Make changes to the page when the current user
      // is in the 'pro' access group.
      if(user.access_groups.includes('pro') {
        
        // Do whatever you want to your page
        
      }
    
      // Make changes to the page when the current user
      // is NOT in the 'pro' access group. ( notice the ! operator )
      if(!user.access_groups.includes('pro') {
        
        // Do whatever you want to your page
        
      }    
      
    }
    
  }]); 
</script>
```

## Conditional Visibility

This technique can be used with custom code to **hide**, **show**, **create**, or **remove** elements.

### Displaying certain elements only to users in a specific access group

> Let's suppose you have several elements that you only want to appear when the user is in an access group named `pro`, and you want those elements deleted from the DOM otherwise.&#x20;

Setup;

* Create a global class, we'll call it `access-group-pro` for simplicity.&#x20;
* Assign it to all elements that you want to appear only for your `pro` access group members.
* Set the style to display: none, so that it is initially hidden, until access group can be determined.&#x20;

{% hint style="info" %}
For this type of operation, [global classes](https://university.webflow.com/lesson/web-styling-using-classes?topics=layout-design#how-to-create-a-global-class) are quite useful since they can be applied on top of other class arrangements. Alternatively, simply wrap your elements in a DIV and assign your `pro-users` class.&#x20;
{% endhint %}

{% code overflow="wrap" %}
```html
<script> 
window.sa5.push(['userInfoChanged', 
  (user) => {
    
    // Check to see if access_groups info is loaded
    if(user.user_data_loaded.access_groups) {
  
      // Find all elements tagged [access-group]
      // and set the inner text to YES | NO
      const elements = document.querySelectorAll('.access-group-pro');
      elements.forEach(element => {
      
        if(user.access_groups.includes('pro')) {
        
          // If the user is in the 'pro' access group, remove our global class
          // this will make the element visible
          element.classList.remove('access-group-pro');
          
        } else {
        
          // If the user is NOT in the 'pro' access group, remove the element
          element.remove();
          
        }
      
      });
      
    }
    
  }]); 
</script>
```
{% endcode %}

{% hint style="warning" %}
**SECURITY:** if you are working with any form of _sensitive_ data, this is not a means to secure that data. Even removing the element will not prevent prying eyes from finding it if they simply disable javascript and examine your page source.&#x20;
{% endhint %}



## Future Ideas

We're looking at adding conditional visibility support to  SA5's Data-Binding lib. Currently our thinking is this;

* Add two new attributes;
  * `wfu-bind-show` will display an element, only if its data-bound value is truthy
  * `wfu-bind-hide` will hide an element if its data-bound value is truthy
* Add a new internal binding resolver piece to the architecture which is source-aware. Regarding the User Object, it will resolve the `access_groups` array into a bindable boolean value.&#x20;

This would support attribute constructions like;

`wfu-bind-hide` = `$user.access_groups.basic`

With this you can make elements conditionally visible on the basis of a single access group.&#x20;

{% hint style="success" %}
The reason for both a **show** and a **hide** variant is that it allows easily for a default state.&#x20;
{% endhint %}

{% hint style="info" %}
Truthy basically evaluates in the same as JavaScript's truthy, however SA5 expands on this slightly.&#x20;
{% endhint %}

{% hint style="info" %}
In the future we may consider more complex specifiers like multiple groups with a boolean AND;

e.g. `$user.access_groups.basic+pro`

A boolean OR;

e.g. `$user.access_groups.basic|pro`

And check-modifiers like boolean NOT;

e.g. `$user.access_groups.basic+!pro`

However at this point you would handle these situations using custom code.&#x20;
{% endhint %}

Later, deprecate `[wfu-show-logged-in]` with an SA5 Data-Binding approach, e.g.

`wfu-bind-show` = `$user.logged_in`

## Routing

{% hint style="info" %}
This is a bit of a beefier design change as we've just built a routing engine as part of the upcoming Detect lib. We'd want to separate that into its own module and likely move it into SA5 Core. As a result, we need to design this piece carefully.&#x20;
{% endhint %}

Use cases;&#x20;

* On entry into any page, e.g. `/my-page` redirect the user based on their presence / absence from an access group.&#x20;
* Modify URLs and button links depending on a user's presence / absence from an access group.&#x20;

### Zoning

This feature would probably benefit from some concept of zoning as a part of the routing architecture, so that you can broadly group pages and elements into an access zone. This would work in conjunction with Webflow's current access-group gating.&#x20;





