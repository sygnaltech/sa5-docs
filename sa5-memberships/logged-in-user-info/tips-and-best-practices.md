---
description: Best Practices Using SA5's User Info Library
---

# Tips & Best Practices

## Use the `userInfoChanged` Callback Effectively

If you want to make special use of user data in your custom code, SA5's `userInfoChanged` callback is the best place to obtain that data once it's loaded.

```html
<!-- Sygnal Attributes 5 | Memberships | User Info Changed Event -->
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['userInfoChanged', 
  (user) => {
    // Check to verify the fields you need are loaded (see below)
    if(user.user_data_loaded.custom_fields) {
        // Do something with custom fields 
        // ...
    	return;
    }
  }]); 
</script>
```

Note that this function will be called _several_ times as the user information is assembled from multiple sources _asynchronously_. This is more robust and more performant as it allows you to use information as soon as it's available, rather than waiting for everything to load.&#x20;

## How to determine when the data you need is loaded

For convenience, the User object contains metadata describing what has already been loaded. This is stored in the `user_data_loaded` sub-object, which contains 4 fields;

* `user_data_loaded.email` is true if the user's email address has been loaded
* `user_data_loaded.account_info` indicates whether basic account-info has been loaded, including the user's name and email-marketing preferences.&#x20;
* `user_data_loaded.custom_fields` is true if the user's custom fields have been loaded. These are any custom-defined fields you've defined in Webflow memberships.
* `user_data_loaded.access_groups` is true if the user's access groups have been loaded ( not yet supported ).

To use that in your callback, just check for the kind of data you're needing, before you attempt to use it. This is how to determine if e.g. `user.name` is blank, or just not loaded yet. &#x20;

## Site-wide v. Page-specific Callbacks

In some cases, you may want a site-wide handler that display information on all pages, such as the user's name in the nav. In other cases, you want special code to run only on a specific page.&#x20;

SA5 was designed to support eventing at both levels. Simply repeat the code block pattern shown above site-wide or on any page, and both handlers will be called.&#x20;

{% hint style="info" %}
**IMPORTANT:** We use this feature regularly at Sygnal however it has not widely been tested by the BETA community. Use with caution.&#x20;
{% endhint %}

## <mark style="color:red;">DEPRECATED</mark> - SA4 Notes

{% hint style="warning" %}
SA5 Upgrade changes how callback events work, so the docs below are considered out of date.&#x20;
{% endhint %}

```html
<script>
async function userInfoUpdatedSiteCallback(user) {
   
  // Check for the fields you needed - see above
  if(user.user_data_loaded.custom_fields) {
    // Your code here
    // ...
    return;
  }
 
  // Call page user data callback, if existing 
  if (window.userInfoUpdatedPageCallback)
  	window.userInfoUpdatedPageCallback(user);
  
} 
</script>
```

## Site-wide v. Page-specific Callbacks

_Separate site-wide v. page-level user data processing._

A common need is to have special page-level user data processing to build a dashboard or other user-specific information- however those element only exist on one page.

```html
<script>
async function userInfoUpdatedSiteCallback(user) {

  /// ...
  
  // On pages where you've defined a userInfoUpdatedPageCallback
  // function, it will be called and passed the user object
  // for page level processing  
  if (window.userInfoUpdatedPageCallback)
  	window.userInfoUpdatedPageCallback(user);
  
} 
</script>
```

On your specific page, your function might then look like this;

{% code overflow="wrap" %}
```html
// Some code
<script>
async function userInfoUpdatedPageCallback(user) {

  console.log("page callback."); 
  
} 
</script>
```
{% endcode %}

Keep in mind, in JS you can do anything you want with the user data. Modify tracking URLs, pre-populate form fields, customize user experiences and so on.&#x20;

