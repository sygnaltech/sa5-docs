# Advanced Log-In & Sign-Up Flow

{% embed url="https://wfu.sygnal.com/docs/webflow-membership/advanced-login-flow/" %}

{% hint style="warning" %}
BETA - While Memberships is in BETA, this library will track that BETA status.
{% endhint %}

This feature allows you to enhance the Sign-Up / Log-In flow.

You can;

* Take users to a special page on their first log-in
* Take users to a member home page on subsequent log-ins
* Have users return to the current page, after log-in

NOTE: There are two primary contexts for login, which we describe as explicit, and implicit. Explicit is when the user clicks a login button, or specifically requests log-in. Implicit is when the user requested a secure page, and Webflow redirect them to login to verify their access.

Implicit login flows are important, and are protected from interference.

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

This libary is not attributes based, but rather has routing configuration options in its setup.

There are currently two configurations options;

* `routeAfterLogin` - specifies an optional path to redirect users after an explicit login.
  * Recognizes a special path of `.`, which means, return to the current page.
* `routeAfterFirstLogin` - specifies an optional path for the first time a user logs in.

### Getting Started ( LOCODE ) <a href="#getting-started-locode" id="getting-started-locode"></a>

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

Add this script to the custom code HEAD of your site.

```
<!-- Membership routing -->
<script type="module">
import { WfuMembershipRouting } from 'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/src/modules/webflow-membership-routing.js';
new WfuMembershipRouting({
    routeAfterLogin: "/u/home",
    routeAfterFirstLogin: "/u/new"
}).routeUser();
</script>
```

Configure the routing options to paths you prefer. These can be secured pages (which require login), or un-secured.

Note that if you use a secured page, you will want to make certain that all of the users you redirect there have the appropriate access group.

See notes above.

\
