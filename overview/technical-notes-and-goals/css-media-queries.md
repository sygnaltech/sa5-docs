---
description: All the things we can do with them.
---

# CSS Media Queries

Media selectors or media queries in CSS are used to apply different styles for different devices or device characteristics.&#x20;

Webflow makes heavy use of them in its responsive breakpoint architecture, but it only uses the **viewport width**. Other device characteristics are not supported as "contexts" that you can design for.

One of our objectives with SA is to expand on these capabilities and support certain capabilities in orientation, aspect ratio, and so on.&#x20;

But there are many!&#x20;

1. **Width and Height of the viewport**: This is probably the most common use of media queries. You can use `min-width`, `max-width`, `min-height`, and `max-height` to apply different styles based on the size of the browser window.
2. **Width and Height of the device**: Similar to the viewport, but for the physical dimensions of the device screen, you can use `min-device-width`, `max-device-width`, `min-device-height`, and `max-device-height`.
3. **Orientation**: You can check if the device is in landscape or portrait mode.
4. **Resolution**: You can apply different styles for devices with different screen resolutions using `min-resolution` or `max-resolution`.
5. **Aspect Ratio**: You can use `aspect-ratio`, `min-aspect-ratio`, and `max-aspect-ratio` to apply styles based on the width-to-height ratio of the viewport, and `device-aspect-ratio`, `min-device-aspect-ratio`, and `max-device-aspect-ratio` for the device screen.
6. **Color**: You can query the number of bits per color component of the output device or the color index using `color`, `min-color`, and `max-color`.
7. **Monochrome**: You can query the number of bits per pixel in a monochrome frame buffer using `monochrome`, `min-monochrome`, and `max-monochrome`.
8. **Scan Process**: You can differentiate between interlaced and progressive scan televisions using the `scan` media feature.
9. **Grid**: You can query whether the output device is grid or bitmap.
10. **Light Level**: You can apply different styles depending on the ambient light level of the device environment (like `dim`, `normal`, `washed`).
11. **Pointer**: You can apply different styles based on the presence and accuracy of a pointing device like a mouse (`none`, `coarse`, `fine`).

\
