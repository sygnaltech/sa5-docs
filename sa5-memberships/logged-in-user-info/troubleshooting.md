---
description: Troubleshooting and FAQs for SA5's Current User Info.
---

# Troubleshooting

## Can't access User Custom Fields

> I'm not getting the custom user fields in my user object data

1. Make certain you have the custom user fields placed on your /user-account page.
   * They can be placed inside of a display: none DIV, but they must be on the page.
2. Make certain to you have logged out and logged in, for the new User Data to load

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





