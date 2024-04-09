# Hyperflow Geo



#### Setting Up Cloudflare IP Geolocation

To make use of this feature, you first need to ensure that IP Geolocation is enabled in your Cloudflare settings. Here’s how to do it:

1. **Log in** to your Cloudflare dashboard.
2. Navigate to the **Network** tab.
3. Look for the **IP Geolocation** setting and turn it on.

When IP Geolocation is enabled, Cloudflare appends the `CF-IPCountry` header to each request with a two-letter country code (ISO 3166-1 Alpha-2). For example, `US` for the United States, `GB` for Great Britain, etc.

```
fetch('https://ipinfo.io/json?token=<YOUR_TOKEN>')
    .then(response => response.json())
    .then(data => {
        console.log("Country:", data.country);
    });

```



```
addEventListener('fetch', event => {
  event.respondWith(handleRequest(event.request))
})

async function handleRequest(request) {
  // Fetch the original response
  let response = await fetch(request);
  
  // Clone the response so we can modify it
  let responseClone = new Response(response.body, response);
  let countryCode = responseClone.headers.get("CF-IPCountry") || "Unknown";

  // Read the response body
  let body = await responseClone.text();

  // Inject a meta tag or script with the country code
  let injectedBody = body.replace(
    /<\/head>/, 
    `<meta name="country-code" content="${countryCode}">\n</head>`
  );

  // Return modified response
  return new Response(injectedBody, {
    status: response.status,
    statusText: response.statusText,
    headers: response.headers
  });
}

```



```
document.addEventListener('DOMContentLoaded', function() {
  var countryCode = document.querySelector('meta[name="country-code"]').getAttribute('content');
  console.log('Country Code:', countryCode);
});
```

#### Accessing GeoIP Data in Cloudflare

Cloudflare passes some of this data through HTTP request headers when the IP Geolocation feature is enabled. The most commonly used header is the `CF-IPCountry` header, which provides the country code. However, if you need more detailed geolocation data (like city or postal code), you might need to use other services or Cloudflare Workers to fetch and pass this data as custom headers or embed it into your pages.

#### Information Provided by Cloudflare GeoIP

1. **Country Code**: The two-letter ISO 3166-1 alpha-2 country code (e.g., `US` for the United States, `GB` for Great Britain). This is the most commonly used piece of data for basic geographical restrictions or customizations.
2. **Country Name**: The full name of the country associated with the IP address.
3. **Subdivision Name**: Names of the primary subdivisions of the country, such as states in the United States or provinces in Canada. This might be provided as codes aligned with ISO 3166-2 (not always available).
4. **City Name**: The name of the city (when available). This can be used for more granular geo-targeting within specific urban areas.
5. **Postal Code**: The postal code associated with the IP address, which can be used for very specific regional targeting and shipping calculations.
6. **Latitude and Longitude**: The approximate coordinates of the location associated with the IP address. These are not precise but can be used for regional sorting and filtering.
7. **Time Zone**: The time zone associated with the location, given in IANA Time Zone Database format (e.g., `America/New_York`). This is useful for displaying local times on your website or for logging events in local time.
8. **Continent Code**: The two-letter code for the continent on which the IP is located (e.g., `NA` for North America, `EU` for Europe).

#### Use Cases for Cloudflare GeoIP Data

* **Content Localization**: Adjusting the language or content based on the visitor's country.
* **Currency Conversion**: Displaying prices in the local currency.
* **Regulatory Compliance**: Ensuring content complies with local laws (e.g., GDPR in Europe).
* **Market Analysis**: Understanding where your visitors are coming from to tailor marketing strategies.
* **Traffic Redirection**: Directing visitors to country-specific subdomains or mirrors to optimize load times and server response.

Cloudflare's GeoIP capabilities are robust enough for many common use cases, and its integration at the CDN level allows for efficient processing without the need for additional backend logic. However, for more specific needs, additional integration with dedicated GeoIP services may be required.



