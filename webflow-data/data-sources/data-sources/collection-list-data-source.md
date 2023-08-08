---
description: Create and Use Custom Collection List Data Sources
---

# Collection List Data Source

SA5 allows you to create a Data Source from any Webflow Collection List.&#x20;

## How to Create a Collection List Data Source <a href="#how-to-create-a-collection-list-data-source" id="how-to-create-a-collection-list-data-source"></a>

Collection List Data Sources are defined item-by-item, by placing a HTML Embed within the collection list item itself.&#x20;

In the Webflow designer;

1. Create a Webflow **Collection List**. Put it somewhere you can find easily. If you want to hide it from view, consider making it the very last element in your page.
2. Bind it to the **Collection** you want to access data from.
3. In the Collection List Item, add an **HTML Embed** element.
4. Paste the following code into the **HTML Embed**.

{% code overflow="wrap" %}
```html
<script type="wfu-data-item" wfu-data-version="1" wfu-data-dsn="..." wfu-data-item-id="...">
{
  "name": "...",
  "slug": "...", 
  ...
}
</script>
```
{% endcode %}

Where you see `...`, set these fields as follows;

* `wfu-data-dsn` - set a string name you prefer for your DSN, e.g. events. Avoid spaces and keep it simple. It can be the same as your CMS collection slug if you like.&#x20;
* `wfu-data-item-id` - use the **Add Field** widget at the top right of the Embed element to insert these item `slug`.&#x20;
* Do the same for the `name` and `slug` in the body.
* Add your additional fields in the same way to the body of the JSON, inserting the dynamic data with **Add Field** for each field.&#x20;

Tips;&#x20;

* In naming your dsn and fields, give each a unique, recognizable name. I recommend all lowercase letters, no spaces or special characters. For example `blogposts` and `products` are good names.&#x20;
* Make certain there are no spaces between your inserted tag, and the double quotes `"`.

## Demonstration

For a demo of a collection list data source;

{% embed url="https://data-binding.webflow.io/cms?" %}

{% embed url="https://webflow.com/made-in-webflow/website/data-binding" %}

## Limitations

Webflow's HTML Embeds and field insertions are automatically HTML-encoded. This is different from JSON-encoding and may present problems.&#x20;

e.g.&#x20;

* Characters like & become \&amp;
* < becomes \&lt;
* " is not encoded, but is an important JSON delimiter&#x20;

{% hint style="warning" %}
Avoid string values that contain double-quotes ( `"` ) &#x20;
{% endhint %}

## Tips & Best Practices <a href="#advanced-notes" id="advanced-notes"></a>

You can create as many collection data-sources as you want, but make certain they are each named differently. Webflow does have a limit on the number of Collection Lists per page, and these will count towards that.

If you happen to already have a collection list on the page that displays exactly the data you want, you can use that Collection List as your datasource. Simply put your Embed block there, and apply the `wfu-data` attribute to the Collection List. Don’t mark the Collection List as invisible, however you can mark the Embed element as invisible to avoid a messy look in your Designer.

If you use your data-source on multiple pages, you can build your Collection List into a Component. Wrap your Collection list in a DIV, and turn the DIV into a Component. This will allow you to more easily access that outmost Collection List element if you need to.&#x20;

Once you’re all setup, you can make the entire Collection List invisible if you prefer. Simply select the outermost Collection List element and mark it as invisible on all devices. If you do this, you won’t see it anymore in the Webflow designer, but you can select it in the left-side Navigator.

If you’ve hidden your Collection List, or your Embed, remember they’re always available in your left-side navigation.

## Large Collection Lists

**Webflow's Collection Lists have a limit of 100 items.**&#x20;

If you have a Collection List-based data source which is larger than this, one way to support this is to create several lists, with the same configuration. SA5 will work seamlessly across the lists.&#x20;

Set this up by defining a range for each of the lists, 1 - 100, 101 - 200, 201 - 300, etc.&#x20;

{% hint style="info" %}
Don't go overboard with this, there is a maximum of 20 total collection lists per page.&#x20;
{% endhint %}



### &#x20;<a href="#ways-to-use-your-data" id="ways-to-use-your-data"></a>
