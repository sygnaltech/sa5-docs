---
description: Route Visitors and Display Conditional Elements Based on Country or City.
---

# GTM Events ❺🧪

{% hint style="danger" %}
**UNDER DEVELOPMENT**\
Watch this space.
{% endhint %}



## Use Cases

* Route visitors to a Country-specific home page
* Route visitors to a City-specific contact-us page

## Feature Roadmap

{% tabs %}
{% tab title="Completed" %}
* Route user by Country
* Routing table support
  * Supports routing any defined path, e.g. /about to any Geo-specific variants you have, e.g. `/about/gb`, `/about/au`, `/jp/about`.&#x20;
  * Routed sources and destinations are unlimited, no enforced path rules.&#x20;
* Standardized GeoInfo object, to consistently describe the detection regardless of the GeoIP handler source&#x20;
* Cached responses, for minimal GeoIP service traffic
  * One request per unique user&#x20;

GeoIP handlers;

* IPInfo support. 50,000 requests/mo free.&#x20;
{% endtab %}

{% tab title="Planned" %}
* Route user by Continent
* Route user by City
* Cache duration as a setting
* Named route efficiency
  * Modify page paths on e.g. Home / to the routed page variant, to avoid unnecessary redirects. &#x20;

Override support;

* The ability to apply the current setting to a Dropdown, and automatically indicate the current Country, City, etc.
* The ability to change country, city, etc and have that override the detected settings.&#x20;

GeoIP handlers;

* Support for multiple Geoip handlers&#x20;
  * Ability to select in config
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

### Routing Rules

sticky

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







