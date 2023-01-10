# Truncate Text with Ellipsis

{% hint style="danger" %}
This feature can be considered **deprecated** as Webflow now has built-in support for text truncation and ellipsis in its style options.
{% endhint %}

{% embed url="https://wfu.sygnal.com/docs/webflow-html/truncate/" %}

Often, it is desirable to truncate plain text excerpts so that they do not break your layout, particularly when that text is variable ( coming from the CMS ), and when your layout involves a grid arrangement such as a card layout.

Modern CSS does provide a solution for this, but the required settings are not built into the Webflow designer \[yet].

So, here’s a solution that gives you what you need.

NOTE: Custom CSS is applied only in your published site, so you will not see the truncation in the designer.

### Demonstration <a href="#demonstration" id="demonstration"></a>

Demonstration

Text truncated to 3 lines…

Tellus vivamus nulla per habitant pellentesque urna justo vulputate felis eleifend odio.,Sed inceptos nisi aliquet aliquam, erat amet ultrices, mattis rutrum, sed fringilla.,Ultricies auctor quisque tempus ut.,Habitasse tellus rutrum aenean?,Iaculis non vulputate phasellus tincidunt litora facilisis, dapibus faucibus ullamcorper bibendum, at augue bibendum.,Vel consequat porta augue ipsum nibh habitasse.,Fusce etiam quis scelerisque, egestas ligula egestas senectus donec rutrum litora velit, pellentesque ad.,Donec luctus platea ad duis aptent fermentum neque, amet malesuada fringilla per sem pellentesque magna?

Re-Generate

### Usage Notes <a href="#usage-notes" id="usage-notes"></a>

#### `wfu-truncate` attribute <a href="#wfu-truncate-attribute" id="wfu-truncate-attribute"></a>

Use `wfu-truncate` to apply truncation to a text element.

Use a value of `1` to `5` to specify the number of lines.

e.g.;

```
wfu-truncate = 3
```

**Tested on Chrome ONLY.**

### Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for this library, so we’ll use a _no-code_ integration approach.

This is a CSS-only solution.

Add this CSS script to the HEAD of your site or page.

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@3.39/dist/css/webflow-html.css">
```

#### STEP 2 - Apply `wfu-truncate` to your text elements <a href="#step-2---apply-wfu-truncate-to-your-text-elements" id="step-2---apply-wfu-truncate-to-your-text-elements"></a>

See above for details.

\
