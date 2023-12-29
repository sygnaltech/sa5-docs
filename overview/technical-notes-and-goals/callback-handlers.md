---
description: Callback Handlers used to configure and extend SA5 module functionality.
---

# Callback Handlers

SA5 uses callbacks for two purposes;

1. Specifying configuration options, for modules which have them&#x20;
2. Notifying custom code handlers of state changes that the site owner may want to specially handle&#x20;

An example callback;&#x20;

```
<script>
window.sa5 = window.sa5 || [];
window.sa5.push(['getMembershipRoutingConfig', 
  (config) => {
  
    // ... your custom code here ... 

    return config;
  }]); 
</script>
```

## Defined Callbacks

<table><thead><tr><th width="284.3333333333333">Callback Name</th><th width="153">Module</th><th>Use</th></tr></thead><tbody><tr><td>getMembershipRoutingConfig</td><td>Memberships</td><td><a href="../../sa5-user-accounts/advanced-log-in-and-sign-up-flow.md">Configuration</a></td></tr><tr><td>userInfoChanged</td><td>Memberships</td><td><a href="../../sa5-user-accounts/logged-in-user-info/">Event Notification</a> when new user information is loaded</td></tr><tr><td>breakpointChanged</td><td>HTML</td><td><a href="../../sa5-html/breakpoints.md">Event Notification</a> on a breakpoint change</td></tr></tbody></table>
