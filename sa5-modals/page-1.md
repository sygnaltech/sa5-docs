# Side Panels 🧪

{% hint style="info" %}
Might move this to the Elements lib.&#x20;
{% endhint %}

The side-panel concept is;

* A container DIV, containing arbitrary content&#x20;
* Which has a tab piece
  * Typically e.g. 30px x 30px square and icon
* Breakpoint-aware, it only appears at certain breakpoints
* Clicking tab expands tray / collapses tray
* Interactions might collapse tray?  &#x20;
* Tabs are grouped in a panel,&#x20;
  * which can be set to sticky or fixed top
  * left / right / bottom / top
    * expansion direction
    * top right + offset ( left )
    * right top + offset ( down )
    * right middle + offset ( + / - )&#x20;
* Multiple panels for each side? &#x20;

Implementation;&#x20;

* At load,&#x20;
  * button sontainers are created
  * buttons are created
  * panels are created offscreen
  * GSAP wiring is done&#x20;
* At breakpoint, buttons are shown
  * clicking expands / contracts&#x20;



Use cases;

* ToC as in FS ToC
* Filter settings as in FS Filter
* Hours of operation
* Feedback form

