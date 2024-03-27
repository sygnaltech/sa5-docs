# Hyperflow PWA

{% hint style="info" %}
R\&D
{% endhint %}

Progressive Web Apps (PWAs) offer a blend of the best features available on the web and mobile applications. Here's a summary of the capabilities that PWAs provide, making them act and behave much like mobile apps:

[https://progressier.com/](https://progressier.com/)

[https://www.whalesync.com/sync/webflow-supabase](https://www.whalesync.com/sync/webflow-supabase)

## Why PWA's?&#x20;

Progressive Web Apps (PWAs) offer a blend of the best features available on the web and mobile applications. Here's a summary of the capabilities that PWAs provide, making them act and behave much like mobile apps:

#### 1. Installable

PWAs can be added to a device's home screen with an icon, just like native apps. This makes them easily accessible and offers a full-screen experience without the browser UI.

#### 2. Offline Functionality

Through service workers, PWAs can work offline or on low-quality networks. They can cache important resources and content, allowing users to access previously visited pages without an internet connection.

#### 3. Fast Performance

PWAs can significantly improve speed and performance through effective caching, making them feel more like native apps. They can load instantly and respond quickly to user interactions.

#### 4. Push Notifications

PWAs can send push notifications to users' devices, similar to native apps. This feature helps in re-engaging users with customized content and updates.

#### 5. Platform and Device Agnosticism

PWAs run in a web browser, which means they work across all devices and operating systems, providing a consistent user experience whether on Android, iOS, or desktop.

#### 6. Safe and Secure

PWAs are served via HTTPS, ensuring that the content has not been tampered with and user interaction with the app is secure.

#### 7. Discoverability

Being part of the web, PWAs can be found through search engines, which is a significant advantage over native apps that require direct download from an app store.

#### 8. Easy to Update

Unlike native apps that require users to download updates from an app store, PWAs update "on the fly." When a user accesses a PWA, they are always interacting with the most current version.

#### 9. No App Store Submission

PWAs do not need to be submitted to app stores like Google Play or the Apple App Store. This simplifies the process and eliminates waiting for app approval or adhering to specific store guidelines.

[https://developer.mozilla.org/en-US/docs/Web/Progressive\_web\_apps](https://developer.mozilla.org/en-US/docs/Web/Progressive\_web\_apps)

and Google Developers has a comprehensive introduction and tutorials on building your first PWA.

## Technical Notes

Modify Manifest.json

* ? What is specifically needed for a PWA
* ? Are there any Webflow operational conflicts

```
// Some code
{
  "short_name": "App",
  "name": "My Progressive Web App",
  "icons": [
    {
      "src": "icon/lowres.webp",
      "sizes": "48x48",
      "type": "image/webp"
    },
    {
      "src": "icon/hd_hi.ico",
      "sizes": "72x72 96x96 128x128 256x256",
      "type": "image/x-icon"
    }
  ],
  "start_url": "/index.html",
  "background_color": "#FFFFFF",
  "display": "standalone",
  "scope": "/",
  "theme_color": "#000000"
}

```



Service-worker.js&#x20;



```
// Some code

self.addEventListener('install', (e) => {
  e.waitUntil(
    caches.open('my-pwa-cache').then((cache) => {
      return cache.addAll([
        '/',
        '/index.html',
        '/styles/main.css',
        '/script/main.js',
        '/images/logo.png',
        // List other assets
      ]);
    })
  );
});

self.addEventListener('fetch', (e) => {
  e.respondWith(
    caches.match(e.request).then((response) => {
      return response || fetch(e.request);
    })
  );
});


```



Setup

```
// Some code
<link rel="manifest" href="/manifest.json">

```

Register the service worker

The service worker also needs to be registered from your main JavaScript file or within a `<script>` tag in your HTML document. Here's how you might register the service worker:

```
// Some code 
if ('serviceWorker' in navigator) {
  window.addEventListener('load', () => {
    navigator.serviceWorker.register('/service-worker.js').then(registration => {
      console.log('ServiceWorker registration successful with scope: ', registration.scope);
    }, err => {
      console.log('ServiceWorker registration failed: ', err);
    });
  });
}

```





