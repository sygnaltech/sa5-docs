---
description: Get the Access Groups of the Currently Logged-In User
---

# Access Groups \[ BETA ]

{% hint style="info" %}
**BETA TESTING**\
This feature is in BETA. and not recommended for use on production sites.  &#x20;
{% endhint %}

SA5's new **Access Groups** feature adds access group information into the User Info object, and makes it available to you in the callback.&#x20;

From there, you write any custom code you like to hide elements, show elements, redirect users away from pages you do not want them on, and so on.&#x20;

As a best practice, you can use the `user.user_data_loaded.access_groups` to determine if access group loading has completed. It will be true once that portion of the user object is loaded, and then you can check the `user.access_groups` array to see which groups they are a member of.

Later, depending on the use cases shared in the forum, we plan to add attributes-based features like access-group-based conditional visibility, and possibly access-group-based routing. &#x20;

{% hint style="success" %}
**BETA TEAM - WE NEED YOUR FEEDBACK!**

In particular, we need;

* Feedback on the feature and setup process
* Feedback on this part of the documentation
* Use cases for how you want to use Access Groups in controlling routing access, conditional visibility, etc. &#x20;

[Post in the SA5 forum here](https://sygnal-attr.discourse.group/)
{% endhint %}

In a similar fashion to the Custom User Fields, SA5'S Access Groups feature requires a specific setup approach in order to work. Make certain to follow the setup precisely.&#x20;

## How SA5's Access Groups Feature Works

Webflow does not provide Access Groups information in the `/user-account` page so we use a different approach to discern the Access Groups that the current user is a member of.

The underlying strategy is to setup and query a set of _known pages_ that each have specific paths and access rights settings. If the user has access, we know they are a member of that Access Group.

By default these _known pages_ are setup under a special subdirectory named `/sa5-ag`. You will need one ( empty ) page for each of your Access Groups, and each of those pages;&#x20;

* MUST have the same exact slug as the Access Group's slug, e.g. `premium`
* MUST be configured for access ONLY by members of that Access Group

## Setting Up Access Groups

For example, if you have 4 access groups, and their **slugs** are `free`, `basic`, `pro` and `premium`, then you would;

### STEP 1 - Setup the SA5 Access Group Folder & Pages

* Create your Access Groups in Webflow, and write down an exact list of the slugs for each. Keep them short and sweet, and life will be simpler. &#x20;
* Create a folder at the root of your site with the slug `sa5-ag`.&#x20;
* Inside the folder, create 4 pages, with the following **slugs**.
  * `free`, which you restrict only to the Free access group members
  * `basic`, which you restrict only to the Basic access group members
  * `pro`, which you restrict only to the Pro access group members
  * `premium`, which you restrict only to the Premium access group members

{% hint style="info" %}
In these pages, the **name** of the folder and the names and contents of the pages do not matter. Leave the pages blank. However the **slugs** MUST be precisely set according to the instructions above.&#x20;
{% endhint %}

### STEP 2 - Configure SA5 Memberships

In your SITE-wide before-HEAD custom code, where you load the library, configure **SA5 Memberships** with the list of Access Groups it should check for. This is done with a new Memberships configuration block.

In your script, it will look something like this;

{% code overflow="wrap" %}
```html
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['getMembershipConfig', 
  (config) => {
    config.accessGroupsFolder = '/sa5-ag';
    config.accessGroups = [
      'free', 'basic', 'pro', 'premium'
    ];
    return config;
  }]); 
</script>
```
{% endcode %}

Note that this is not the same configuration block as we use for [Advanced Membership Routing](../advanced-log-in-and-sign-up-flow.md). This callback handler is keyed `getMembershipConfig`, while routing uses `getMembershipRoutingConfig`. They are unrelated and have different configuration options. You can use both, if you are using both features concurrently.&#x20;

There are two options you can configure;

* `config.accessGroupsFolder` defaults to `/sa5-ag`. If you want a different folder slug, you can override that. Make certain the folder you create matches that path.&#x20;
* `config.accessGroups` is an array of your Access Group slugs. You can have 1 or 20, it doesn't matter. Make sure it's a valid JavaScript string array, with comma delimiters. &#x20;

### STEP 3 - Update the Library to BETA & Check Your Work

{% hint style="warning" %}
**IMPORTANT LIBRARY VERSION UPDATE** \
You will need to update your Webflow Memberships library version overall to use this. Do _not_ install multiple copies or versions of the library on the same site.&#x20;
{% endhint %}

{% code overflow="wrap" %}
```html
<!-- Sygnal Attributes 5 | Memberships BETA -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.3.1-beta/dist/css/webflow-membership.css"> 
<script defer src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.3.1-beta/dist/nocode/webflow-membership.js"></script>
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['getMembershipConfig', 
  (config) => {
    config.accessGroupsFolder = '/sa5-ag';
    config.accessGroups = [
      'free', 'basic', 'pro', 'premium'
    ];
    return config;
  }]); 
window.sa5.push(['userInfoChanged', 
  (user) => {
    console.log("USER INFO CHANGED", user); 
  }]);   
</script>
```
{% endcode %}











