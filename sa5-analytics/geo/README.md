---
description: Route Visitors and Display Conditional Elements Based on Country or City.
---

# GTM Events ❺🧪

{% hint style="danger" %}
**UNDER DEVELOPMENT**\
Watch this space.
{% endhint %}

## Goals

* Simplify GTM tracking
  * Keep as much of the configuration as possible designer-accessible
  * Custom attributes
  * Embeds for data structures
* Enable tracking of all kinds of events
* Capture specific metadata, with the goal of being able to use it in analytics, advertising, and reporting systems like GA4&#x20;

## Features ( Current )

* Track click events, with metadata, on anything
* Track load events, with metadata, on anything
* Restrict GTM events to specific breakpoints

## Use Cases

* Track click & display events on your CTAs, and display events, so you can determine conversions
* Pass it through to GA4 for reporting, in combination with other data&#x20;

Future;

* A/B testing&#x20;
* Capture user-specific form data&#x20;

## Usage Notes

{% hint style="info" %}
SA5 simplifies the capture of events and passes them to GTM, however there is still configuration work required in GTM to receive that data, and in end systems like GA4, there is configuration work required to capture and display that data.&#x20;
{% endhint %}

SA5's GTM tracking config in the designer involves two parts;

* An element that you wish to track events on. This _must_ be a container element, such as a DIV.
* An Embed within that element that contains the detailed data for the dataLayer. The Embed must contain a script element with a type of `sa5/gtm-data` and there must be only one of these within your tracked elemen.

The reason for this is that we want

```html
<script type="sa5/gtm-data">
{
  "event": "banner_interaction",
  "banner_name": "sticky",
  "interaction_type": "click"
}
</script>
```

{% hint style="info" %}
This MUST be valid JSON.&#x20;
{% endhint %}



wfu-gtm-event

* click - fires on a mouse click
* load - fires on page load

Future;

scroll, interactions visibility&#x20;

wfu-gtm-event-id

Future.

wfu-gtm-event-name

Optional. Currently used for logging so that you can&#x20;

Recommended to treat it as an identifier, meaning all-lowercase, and hyphens instead of spaces, e.g. desktop-qr

## wfu-gtm-event-breakpoints

This attribute allows you to restrict the breakpoints that an event will fire on.

It's composed of a string which specifies the breakpoints you want to allow the event on, and each letter defined a breakpoint;

321DTLP

1920+ 1440+ 1280+ desktop 991- tablet 767- landscape 478- portrait



Each breakpoint has an uppercase letter to describe it, in the table below.

Each has a corresponding lowercase letter which describes a range.

For example;

* `D` indicates desktop specifically, i.e. 992px - 1280px.  `d` indicates Desktop-or-larger, 992px+
* `T` indicates tablet, i.e. 768px - 991px. `t` indicates Tablet-or-smaller, 0px - 991px.



<table><thead><tr><th>Breakpoint</th><th width="62"></th><th>Range</th><th width="65"></th><th>Range</th></tr></thead><tbody><tr><td>Mobile Portrait</td><td>P</td><td>0 - 480</td><td>p</td><td>0 - 480</td></tr><tr><td>Mobile Landscape</td><td>L</td><td>481 - 767</td><td>l</td><td>0 - 767</td></tr><tr><td>Tablet</td><td>T</td><td>768 - 991</td><td>t</td><td>0 - 991</td></tr><tr><td>Desktop</td><td>D</td><td>992 - 1280</td><td>d</td><td>992 - unlimited</td></tr><tr><td>Medium Large</td><td>M</td><td>1281 - 1440</td><td>m</td><td>1281 - unlimited</td></tr><tr><td>Large</td><td>R</td><td>1441 - 1920</td><td>r</td><td>1441 - unlimited</td></tr><tr><td>Extra Large</td><td>X</td><td>1921 - unlimited</td><td>x</td><td>1921 - unlimited</td></tr></tbody></table>

You can combine these into any arrangement to describe the breakpoints you want.

For example;

* `Td` would mean Tablet and anything Desktop or larger
* `PD` would mean only Mobile Portrait, and Desktop, but not Landscape, Tablet, or larger breakpoints.

## Feature Roadmap

{% tabs %}
{% tab title="Completed" %}
Events supported;

* click tracking
* load tracking

Other;

* Arbitrary data capture
{% endtab %}

{% tab title="Planned" %}
Add events support;&#x20;

* Forms
* Scroll into view ( element seen )
* Script-triggered events
{% endtab %}

{% tab title="Considering" %}
Developer support;

* Expose and document the Detect objects for use in code, e.g.;
  * Data-binding support, populate a form's Zip code field, select a country, etc.&#x20;
  * Auto-center maps&#x20;
* Automatic Filter-binding support for FS-Filter

GeoZone definitions;&#x20;

* Collection of countries, cities, zips, etc into a Zone, like "Europe"&#x20;

GeoIP handlers;

* Ability to select the GeoIP handler dynamically in config&#x20;
* Fallback handlers&#x20;
{% endtab %}

{% tab title="More Ideas" %}
GeoZone definitions;

* Point-and-radius
* Sort list by nearest ( branch locators, etc. )&#x20;
* Zip to data chaining&#x20;

GeoIP handlers;

* Possibly a Sygnal-specific Geoip handler&#x20;
{% endtab %}
{% endtabs %}



## Usage Notes <a href="#usage-notes" id="usage-notes"></a>

###

wfu-gtm-event = click







Inside of the element with the attribute, place one and only one of these

TODO support multiple?&#x20;

```
// Some code
sticky
<script type="sa5/gtm-data">
{
  "event": "banner_interaction",
  "banner_name": "desktop QR",
  "interaction_type": "close"
}
</script>


```

## GTM Setup

#### Create Data Layer Variables in GTM

For each piece of data you want to capture (e.g., `banner_name`, `interaction_type`, `variant`), you'll need to create a corresponding Data Layer Variable in GTM:

* Go to Variables in your GTM dashboard.
* Click "New" to create a new variable.
* Select "Data Layer Variable" as the variable type.
* Enter the Data Layer Variable Name exactly as it appears in your data layer push (e.g., `banner_name`).
* Name your variable (e.g., `DLV - Banner Name`) and save.

#### . Create a Trigger for `banner_interaction` Events

* Go to Triggers in your GTM dashboard.
* Click "New" to create a new trigger.
* Select "Custom Event" as the trigger type.
* For the "Event Name," enter `banner_interaction`—this should match exactly what you're pushing to the data layer.
* Choose "All Custom Events" to trigger for all instances of `banner_interaction`.
* Name your trigger (e.g., `Trigger - Banner Interaction`) and save.

#### Create a GA4 Event Tag

* Go to Tags in your GTM dashboard and click "New."
* Choose "GA4 Event" as the tag type (make sure you've already set up a GA4 Configuration tag).
* Select your GA4 Configuration Tag in the "Configuration Tag" setting.
* For "Event Name," you can either directly use `banner_interaction` or define a variable if you plan to dynamically name events.
* Under "Event Parameters," add parameters for each piece of data you want to send to GA4 (e.g., `banner_name`, `interaction_type`, `variant`). Use the Data Layer Variables you created earlier as values.
* In the "Triggering" section, select the `banner_interaction` trigger you created.
* Name your tag (e.g., `Tag - GA4 Banner Interaction Event`) and save.

#### Test & Publish

* Use the "Preview" mode in GTM to test your setup. Make sure that the `banner_interaction` events are triggering the GA4 tag correctly and that the data appears as expected in your GA4 debug view or real-time events report.
* Once you've verified that everything is working as expected, publish your changes in GTM.

## GA4 Setup

Reports

With Google Tag Manager (GTM) set up to send your banner interaction data to Google Analytics 4 (GA4), the next step is to view, capture, and report on this data within GA4. Here's how to do it:

#### Step 1: Verify Event Collection in GA4

First, ensure that the events you're sending from GTM are arriving in GA4:

1. Go to your GA4 Property.
2. Navigate to the "Events" section in the menu on the left.
3. Look for your event (e.g., `banner_interaction`). It might take some time for new events to appear if they've just been set up.

#### Step 2: Create Custom Dimensions (if needed)

If you're sending additional data with your events (e.g., `banner_name`, `interaction_type`, `variant`), you might want to create custom dimensions in GA4 to capture these details:

1. In GA4, navigate to "Configure" then "Custom Definitions".
2. Click "Create custom dimensions".
3. Fill out the details for each piece of additional data you're sending. The dimension name should match the parameter names you're sending from GTM (e.g., `banner_name`).
4. Save your custom dimensions.

\
With Google Tag Manager (GTM) set up to send your banner interaction data to Google Analytics 4 (GA4), the next step is to view, capture, and report on this data within GA4. Here's how to do it:

#### Step 1: Verify Event Collection in GA4

First, ensure that the events you're sending from GTM are arriving in GA4:

1. Go to your GA4 Property.
2. Navigate to the "Events" section in the menu on the left.
3. Look for your event (e.g., `banner_interaction`). It might take some time for new events to appear if they've just been set up.

#### Step 2: Create Custom Dimensions (if needed)

If you're sending additional data with your events (e.g., `banner_name`, `interaction_type`, `variant`), you might want to create custom dimensions in GA4 to capture these details:

1. In GA4, navigate to "Configure" then "Custom Definitions".
2. Click "Create custom dimensions".
3. Fill out the details for each piece of additional data you're sending. The dimension name should match the parameter names you're sending from GTM (e.g., `banner_name`).
4. Save your custom dimensions.

#### Step 3: Using the Data in Reports

To view and analyze your event data:

**Exploration Reports:**

1. Navigate to "Explore" from the left menu.
2. Create a new exploration or use an existing template.
3. In the variable settings, add your event and any custom dimensions as dimensions, and choose metrics (e.g., Event count).
4. Arrange the dimensions and metrics to analyze your data, such as by `banner_name` or `interaction_type`.

**Custom Reports:**

1. For more persistent reporting, navigate to "Reports" then "Library".
2. Create a new report or modify an existing one.
3. Add your event as a dimension and select appropriate metrics.
4. Customize the report further by adding filters or breakdowns by your custom dimensions.

#### Step 4: Real-Time Reporting

For immediate feedback:

1. Navigate to the "Realtime" section.
2. Look for your event under "Event count in the last 30 minutes".
3. Use the filter option to drill down into specific interactions or banners.

#### Step 5: Setting Up Audiences (Optional)

If you want to create audiences based on specific interactions for remarketing or analysis:

1. Navigate to "Configure" then "Audiences".
2. Create a new audience and use your event data and custom dimensions as criteria (e.g., users who clicked on a specific banner).

#### Step 6: Conversion Events (Optional)

If certain banner interactions are important conversions:

1. Navigate to "Configure" then "Conversions".
2. Click "New conversion event" and enter the name of the event you want to mark as a conversion.

Remember, the specifics of how you set up your reports and analyses will depend on your unique business questions and the insights you're seeking to gain from the data. By following these steps, you'll be well-equipped to capture and report on banner interaction data in GA4, leveraging the power of GTM for comprehensive web analytics.







