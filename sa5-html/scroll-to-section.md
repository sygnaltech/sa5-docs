# Scroll to Section

Scrolling scenarios

* Specific pages, often the homepage hav sections that we want to directly scroll to in the global nav
* All pages have



Solutions;

* Must handle direct navigation\
  e.g. `https://www.mysite.com/#contact`&#x20;
* Must handle top-nav navigation from that page's nav bar

Ideally,&#x20;

*
* Should work perfectly on both staging and production, e.g. the origin does not need to be part of the URL
* We do not want to have to handle in-page scrolling v. cross-page scrolling separately &#x20;
* CMS-link compatible&#x20;
* Keep the current state nav depending on the section you're on&#x20;

Offset;

* Support offsetting the scroll position for a fixed nav
* Support sticky navs as well
* Auto-calculate ( like Webflow does ) or allow a manual specification, stored on the body element&#x20;

Options;

* Hide the `#hash`&#x20;
* Delay re-scroll, used for lazy-load&#x20;
* Just remove lazy-load  ( bandwidth impacts )&#x20;
*

## Usage Notes

* Avoid using the scroll-to-section option in links
* Instead, form your links as relative links

Specific page

e.g. `/#contact`&#x20;

e.g. `/about/#contact`

{% hint style="info" %}
ID's are case-sensitive
{% endhint %}

Current page

e.g. a section that you have on all pages, such as a Contact Us block that is part of your page footer.&#x20;

e.g. `#contact`&#x20;

Note the absence of the forward slash `/`, which is the homepage path.  Here we avoid adding a path that since we want to stay on the current page.&#x20;

Link from another site

e.g. `https://www.mysite.com/#contact`&#x20;

This will also work, and smooth-scroll&#x20;







{% hint style="info" %}
Will these work in the CMS?&#x20;
{% endhint %}



## Technical Notes

```
function scrollToElementWithOffset() {
    console.log('scrollToElementWithOffset triggered');

    // Suppress the automatic hash scrolling behavior on page load
    if (window.location.hash) {
        // Temporarily remove the hash to prevent default jumping
        const originalHash = window.location.hash;
        history.replaceState(null, null, ' '); // Temporarily remove the hash
        console.log('Suppressed initial hash:', originalHash);

        setTimeout(() => {
            // Check if there's a fixed-position element at the top of the body
            const fixedElement = document.querySelector('body > *');
            console.log('First element in body:', fixedElement);

            let offset = 0;
            if (fixedElement) {
                const computedStyle = window.getComputedStyle(fixedElement);
                console.log('Computed style of first element:', computedStyle.position);

                if (computedStyle.position === 'fixed') {
                    offset = fixedElement.offsetHeight;
                    console.log('Fixed element detected with height:', offset);
                } else {
                    console.log('First element is not fixed position');
                }
            } else {
                console.log('No elements found in body');
            }

            // Restore the hash
            history.replaceState(null, null, originalHash);
            console.log('Restored the original hash:', originalHash);

            // Now scroll to the target element with the correct offset
            const element = document.querySelector(originalHash);
            console.log('Target element for hash:', element);

            if (element) {
                // Calculate the target scroll position
                const elementPosition = element.getBoundingClientRect().top + window.scrollY;
                const offsetPosition = elementPosition - offset;
                console.log('Element position:', elementPosition);
                console.log('Offset position:', offsetPosition);

                // Scroll to the position with the offset
                window.scrollTo({
                    top: offsetPosition,
                    behavior: 'smooth'
                });
                console.log('Scrolling to position with offset');
            } else {
                console.log('No element found for the hash:', originalHash);
            }
        }, 0); // Run after the current event loop to ensure the DOM is ready
    } else {
        console.log('No hash in the URL');
    }
}

// Run the function on page load and on hashchange
window.addEventListener('load', scrollToElementWithOffset);
window.addEventListener('hashchange', scrollToElementWithOffset);

```





