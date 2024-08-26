---
description: Troubleshooting and FAQs for SA5's Current User Info.
---

# Troubleshooting

## Enabling & Disabling Debugging

SA5 has built-in debugging, which will emit some deeper information that may be helpful in diagnosing your setup issue. &#x20;

To activate it on your site, append this querystring on any page;

```
?debug=1
```

This will enable debugging only on the machine you are currently on. It will remain on as you navigate through the site, even when you no longer have that querystring.&#x20;

To disable debugging, do the same with;&#x20;

```
?debug=0
```

### Viewing Debug Message Details

SA5's debug messages will appear in the console of your browser's DevTools.

{% hint style="info" %}
Make certain to enable Verbose debugging or many of the detail messages will not be visible to you.&#x20;
{% endhint %}

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>Enable verbose debugging. </p></figcaption></figure>

### Using Debug Messages

Engineers on the SA5 open source project will be able to make use of most of the messages here.  For most users, the most valuable thing is the SA5User objects. &#x20;

You can expand these to view the state of the data at that point in the load, for example does it have the user's email, access groups, name, custom data, and more.&#x20;

The `user_data_loaded` field shows what it has completed loading so you can diagnose issues by comparing this to the data you have.  If `user_data_loaded.access_groups` shows true, but your `access_groups` are empty, you might have a configuration problem with access groups and you'd know to review the setup instructions there.&#x20;

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

## Can't access User Custom Fields

> I'm not getting the custom user fields in my user object data

1. Make certain you have the custom user fields placed on your /user-account page.
   * They can be placed inside of a display: none DIV, but they must be on the page.
2. Make certain to you have logged out and logged in, for the new User Data to load

## User Data _Usually_ Loads, But _Sometimes_ it Doesn't

SA5 User Info depends on Webflow's `/user-account` page, which can be slow.  If Webflow's servers or your network are _too_ slow, then the data may not have been loaded yet when we access it.

To remedy this, you can increase SA5's default delay before the data is read from the `/user-account` page.&#x20;

This is done under the `config.advanced` property...&#x20;

```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['getMembershipConfig', 
  (config) => {
    config.accessGroupsFolder = '/sa5-ag';
    config.accessGroups = [
      'free', 'basic', 'pro', 'premium'
    ];
    config.advanced = {
      accountInfoLoadDelay: 300, // ms
      accountInfoSaveDelay: 500 // ms
    };
    return config;
  }]); 
</script>
```

### What the properties do;&#x20;

**accountInfoLoadDelay** defines the time ( in milliseconds ) that SA5 should wait for Webflow to complete loading the account info in the account info page.  This is the point at which all of the input fields should be populated by webflow.js.&#x20;

**accountInfoSaveDelay** defines the time ( in milliseconds ) that SA5 should wait after account info is updated and saved on the account info page, before re-loading the data to update the User Info object.

{% hint style="success" %}
As of **SA5 User Info v5.4.6**, the configuration will be emitted in the debugging stream so that you can verify your settings.&#x20;
{% endhint %}

## On Webflow's ECommerce Checkout Page, the User's Email shows and then disappears after a second.&#x20;

{% hint style="info" %}
If you're trying to use SA5's data-binding feature on Webflow's ECommerce check-out page to default the checkout email, we've seen a couple of mentions that fields on this page may be getting reset after databinding. If you experience this, here's a general strategy you can use to force it. &#x20;
{% endhint %}

```html
<script>
function forceEmail(email) {
    let checkCount = 0;
    const interval = setInterval(function() {
        const inputField = document.getElementById('wf-ecom-email');

        // If the input field is empty and email is available
        if (inputField.value === '' && email) {
            inputField.value = user.email;
        }

        // Increment the check count
        checkCount++;

        // Keep checking for 4 seconds after page load
        if (checkCount >= 20) {
            clearInterval(interval);
        }
    }, 250);
}

window.sa5 = window.sa5 || [];
window.sa5.push(['userInfoChanged', 
  (user) => {
    forceEmail(user.email);
  }]); 
</script> 
```





