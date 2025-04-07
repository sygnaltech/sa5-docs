# Exit Intent Trigger 🧪





```html
<script type="application/sa+json" handler="trigger.exit-intent" event="exitintent1">
{
  "@context": "https://attr.sygnal.com",
  "@version": "0.1" 
}
</script>
```









## Design Notes&#x20;

### **Common Exit Intent Detection Methods**

1. **Mouse Movement to Top of Viewport (Most Common)**
   * Detects when the user moves their cursor **near the top of the browser window** (towards the close tab button).
   * Ideal for **desktop users**.
   * Not effective on mobile.
2. **Mouse Speed and Direction**
   * Detects **fast cursor movement** toward the browser edges.
   * Useful for **more aggressive detection**.
3. **Lost Focus on Window**
   * Fires when the user **switches tabs or minimizes the window**.
   * Good for detecting intent but can **fire too often** in normal browsing.
4. **Page Visibility API**
   * Detects when the page goes into the background (`visibilitychange` event).
   * Best for **tracking when users switch tabs**.
5. **Back Button Navigation**
   * Detects when users press the **back button** before leaving.
   * Works well for preventing abandonment.
6. **Session Timeout**
   * Detects when the user is inactive for a set time.
   * Useful for **re-engaging users**.





