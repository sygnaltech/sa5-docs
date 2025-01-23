# Inactivity Timer 🧪



Conceptual

* install on every page
* Watches for keyboard, mouse, and touch events&#x20;
* Redirects to a specified home page if there's no activity&#x20;





```html
<script type="application/sa5+json">
{
  "@context": "https://attr.sygnal.com",
  "@type": "KioskConfig",
  "@version": "0.1",
  "homePath": "/kiosk", 
  "userAgent": "KioskApp/1.0", 
  "inactivityTimer": "180"  
}
</script>
```





```
    // Set the inactivity timeout duration in milliseconds (3 minutes)
    const INACTIVITY_TIMEOUT = 3 * 60 * 1000; // 3 minutes
    let inactivityTimer;

    // Function to reset the timer
    function resetInactivityTimer() {
      // Clear the existing timer
      clearTimeout(inactivityTimer);

      // Set a new timer
      inactivityTimer = setTimeout(() => {
        // Redirect to the /kiosk page after the timeout
        window.location.href = "/kiosk";
      }, INACTIVITY_TIMEOUT);
    }

    // Add event listeners for all user interactions
    function setupEventListeners() {
      const events = [
        "mousemove",
        "mousedown",
        "touchstart",
        "touchmove",
        "keydown",
        "scroll"
      ];

      events.forEach(event => {
        window.addEventListener(event, resetInactivityTimer, { passive: true });
      });
    }

    // Initialize the inactivity timer and event listeners
    function initializeInactivityTimer() {
      
     function isKioskMode() {
        return /kiosk/i.test(navigator.userAgent); // Case-insensitive check for "kiosk" in the user agent string
    }
      
      if(!isKioskMode()) {
        console.log("Not kiosk mode."); 
        return; 
      }
      
      if (window.location.pathname === '/kiosk') {
        console.log("Already on /kiosk main page");
        return; 
      }

      console.log("Initialziing kiosk inactivity timer."); 
      
      setupEventListeners();
      resetInactivityTimer(); // Start the timer initially
    }

    // Start the inactivity timer
    initializeInactivityTimer(); 
```



