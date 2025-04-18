---
description: Sygnal's SA5 libraries are delivered on the jsdelivr CDN.
---

# GDPR

{% hint style="success" %}
These notes are for anyone concerned about using CDNs in the EU, due to GDPR regulations.&#x20;
{% endhint %}

In January 2022, a Munich court ruled that a website using Google Fonts violated the GDPR by transmitting users' IP addresses to Google without consent. This decision caused concern among developers about the implications for other CDN services like jsDelivr.

To address these concerns, jsDelivr consulted R\&S Partners, a law firm in Krakow, Poland. The firm clarified that the ruling is specific to the Google Fonts case and does not establish a general precedent across the EU. Each case requires individual assessment.

Key distinctions between Google Fonts and jsDelivr include:

* **Necessity of Data Processing**: jsDelivr processes IP addresses to deliver content efficiently through its global CDN infrastructure. This processing is essential for the service's functionality, unlike Google Fonts, which can be used without connecting to Google's servers.
* **Purpose of Data Use**: jsDelivr uses IP data solely for statistical purposes, such as optimizing server locations. The data is aggregated and deleted promptly, not used for marketing or sold to third parties.
* **Security Measures**: jsDelivr employs encrypted connections and regional servers to minimize risks like man-in-the-middle attacks, enhancing user data protection.

The law firm concluded that jsDelivr's data processing practices align with GDPR requirements, particularly under Article 6(1)(f), which allows processing based on legitimate interests. They recommend that websites using jsDelivr update their privacy policies to inform users about IP address processing for service functionality and security.

In summary, the German court's ruling on Google Fonts does not directly impact jsDelivr. jsDelivr's data handling practices are considered compliant with GDPR, making it safe to use.

## Our Perspective

It's our perspective that it's legally GDPR-compliant to use SA5 in its CDN hosted form.

**However if you should have any requirement to host it differently, SA5 is fully open source and can be downloaded and deployed elsewhere from our Github repo.**&#x20;

{% hint style="info" %}
Finsweet's libraries also use JSDelivr as their chosen CDN.&#x20;
{% endhint %}

## References&#x20;

[https://www.jsdelivr.com/blog/how-the-german-courts-ruling-on-google-fonts-affects-jsdelivr-and-why-it-is-safe-to-use/](https://www.jsdelivr.com/blog/how-the-german-courts-ruling-on-google-fonts-affects-jsdelivr-and-why-it-is-safe-to-use/)

[https://news.ycombinator.com/item?id=35793009](https://news.ycombinator.com/item?id=35793009)



