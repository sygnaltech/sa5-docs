# Detect Incognito Mode

This is a rarely needed situation, which we refer to as a Dark Site, in reference to the Dark Web- sites that "hide" from the traditional mechanics of discovery, history, tracking, and so on.&#x20;

Here we're focused on detecting Incognito Mode.&#x20;

## Goals

* Detect Incognito mode
  * Various browsers
* Warn user if not in incognito mode
  * Give proceed ( that's fine ) option
  * Give exit option
    * Instructions on how to invoke incognito mode on that browser
    * Clipboard copy URL
    * Purge / replace browser history&#x20;
      * Chain purge
      * Cookies
      * webStorage&#x20;

## Use Cases

**The primary general use case here is to minimize the risk of unwanted browser-history tracking on a site.**&#x20;

There are of course many illicit use cases here, but the scenario we're interested in supporting is domestic abuse hotlines, where someone may seek help and information but needs to be able to do so safely with minimal risk of someone else discovering their investigations.&#x20;

## Implementation Notes

<img src="../.gitbook/assets/file.excalidraw (1) (1) (1) (1) (1) (1).svg" alt="" class="gitbook-drawing">

### Detecting Incognito Mode

Detecting if a browser is in incognito mode is not straightforward, as browsers are designed to prevent detection of incognito mode to protect user privacy. However, there are some heuristics and methods you can use to make an educated guess. Below is an example of how to detect incognito mode in various browsers and how to prevent the user from proceeding if they are not in incognito mode.

#### **Chrome and Edge**

You can use the FileSystem API to detect incognito mode. In incognito mode, the FileSystem API is disabled, and trying to use it will result in an error.



```
function isIncognito(callback) {
    var fs = window.RequestFileSystem || window.webkitRequestFileSystem;
    if (!fs) {
        callback(false);
        return;
    }
    fs(window.TEMPORARY, 100, function () {
        callback(false);
    }, function () {
        callback(true);
    });
}

isIncognito(function(isPrivate) {
    if (!isPrivate) {
        alert("Please open this page in incognito mode.");
        window.location.href = 'about:blank';
    } else {
        console.log("You are in incognito mode.");
    }
});

```

#### **Firefox**

Firefox does not disable the FileSystem API, so the above method won't work. Instead, you can check the storage quota, as incognito mode typically has a much smaller quota.&#x20;

```
function isIncognito(callback) {
    var db = indexedDB.open("test");
    db.onerror = function() {
        callback(true);
    };
    db.onsuccess = function() {
        callback(false);
    };
}

isIncognito(function(isPrivate) {
    if (!isPrivate) {
        alert("Please open this page in incognito mode.");
        window.location.href = 'about:blank';
    } else {
        console.log("You are in incognito mode.");
    }
});

```

#### **Safari**

Safari has different limitations in private browsing mode, such as no local storage access. You can test for these limitations.

```
function isIncognito(callback) {
    var isSafari = navigator.vendor && navigator.vendor.indexOf('Apple') > -1 &&
                  navigator.userAgent && !navigator.userAgent.match('CriOS');

    if (isSafari) {
        try {
            window.openDatabase(null, null, null, null);
            callback(false);
        } catch (_) {
            callback(true);
        }
    } else {
        callback(false);
    }
}

isIncognito(function(isPrivate) {
    if (!isPrivate) {
        alert("Please open this page in incognito mode.");
        window.location.href = 'about:blank';
    } else {
        console.log("You are in incognito mode.");
    }
});

```

### Preventing User from Proceeding

If the user is not in incognito mode, you can redirect them to a different page or display a message preventing further interaction.&#x20;

Combining the detection methods for Chrome, Edge, Firefox, and Safari:

```
        function isIncognito(callback) {
            var fs = window.RequestFileSystem || window.webkitRequestFileSystem;
            if (fs) {
                fs(window.TEMPORARY, 100, function () {
                    callback(false);
                }, function () {
                    callback(true);
                });
            } else if (navigator.vendor && navigator.vendor.indexOf('Apple') > -1 &&
                      navigator.userAgent && !navigator.userAgent.match('CriOS')) {
                try {
                    window.openDatabase(null, null, null, null);
                    callback(false);
                } catch (_) {
                    callback(true);
                }
            } else {
                var db = indexedDB.open("test");
                db.onerror = function() {
                    callback(true);
                };
                db.onsuccess = function() {
                    callback(false);
                };
            }
        }

        isIncognito(function(isPrivate) {
            if (!isPrivate) {
                alert("Please open this page in incognito mode.");
                window.location.href = 'about:blank';
            } else {
                console.log("You are in incognito mode.");
            }
        });
```

### History Purge&#x20;



```
// List of random sites to redirect to
const randomSites = [
    'https://www.example1.com',
    'https://www.example2.com',
    'https://www.example3.com'
];

// Function to clear history and redirect
function clearHistoryAndRedirect() {
    // Clear history by navigating back in a loop
    let numberOfEntries = history.length;
    for (let i = 0; i < numberOfEntries; i++) {
        history.back();
    }

    // After history is cleared, use replace to redirect
    setTimeout(() => {
        const randomSite = randomSites[Math.floor(Math.random() * randomSites.length)];
        location.replace(randomSite);
    }, 100); // small delay to ensure history.back() operations complete
}

// Add event listener to the button
document.getElementById('randomRedirectBtn').addEventListener('click', clearHistoryAndRedirect);

```



```
function navigateTo(url) {
    // Change the URL without adding a new history entry
    window.history.replaceState({}, '', url);

    // Load new content dynamically
    loadContent(url);
}

function loadContent(url) {
    // Your logic to load content for the given URL
    // This could be an AJAX request or any other method to dynamically load content
}

// Example usage
navigateTo('/new-page');

```



```
<meta http-equiv="Cache-Control" content="no-store">

```



#### Reverse Proxy

```
Cache-Control: no-store
```

























