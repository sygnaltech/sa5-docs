# Technical Notes







## Detecting Kiosk Mode

Typically we want this explicit, so we use the UserAgent to identify the kiosks.

Which Chrome this is easy;&#x20;











use



```css
/* Touch-based devices (e.g., phones, tablets) */
@media (pointer: coarse) {
  button {
    padding: 20px; /* Larger touch targets */
  }
}

/* Desktop devices with a mouse */
@media (hover: hover) and (pointer: fine) {
  button:hover {
    background-color: lightblue;
  }
}
```







