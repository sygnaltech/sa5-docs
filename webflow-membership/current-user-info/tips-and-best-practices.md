# Tips & Best Practices

## Use the Callback Function Effectively

_The best place to access and make use of user data is in the callback function._

Note that this function will be called _several_ times as the user information is assembled from multiple sources _asynchronously_. This allows you to use information as soon as it's available, rather than waiting for everything to load.

For convenience, the User object contains metadata describing what has already been loaded. This is stored in the `user_data_loaded` sub-object, which contains 4 fields;

* `user_data_loaded.email` is true if the user's email address has been loaded
* `user_data_loaded.account_info` indicates whether basic account-info has been loaded, including the user's name and email-marketing preferences.&#x20;
* `user_data_loaded.custom_fields` is true if the user's custom fields have been loaded. These are any custom-defined fields you've defined in Webflow memberships.
* `user_data_loaded.access_groups` is true if the user's access groups have been loaded ( not yet supported ).

To use that in your callback, just check for the kind of data you're needing, before you attempt to use it. This is how to determine if e.g. `user.name` is blank, or just not loaded yet. &#x20;

```html
<script>
async function userInfoUpdatedSiteCallback(user) {
  
  // General data-binding   
  var dataBinder = new WfuDataBinder().bind(); 
  
  // Check for the fields you needed
  if(!user.user_data_loaded.custom_fields) {
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

