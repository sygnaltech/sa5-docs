# Security Headers



[https://discourse.webflow.com/t/how-to-add-security-headers-in-response/200761/5](https://discourse.webflow.com/t/how-to-add-security-headers-in-response/200761/5)

It is possible to add **X-Frame-Options** header as part of CMS plan

But looks like for adding other custom headers, we need an enterprise plan

BTW , this is how i added X-Frame-Options header

1. Login to webflow > Dashboard > site settings
2. Click on **Publish** > **Advanced Options** > Check **Use secure frame headers**
3. This setting will add X-Frame-Options: SAMEORIGIN to all the pages

