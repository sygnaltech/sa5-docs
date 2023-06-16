# Data-binding Form INPUTs & SELECTs

Data-binding is the original feature that SA was built around. It developed out of a need to populate Form SELECTs with dynamic data from Webflow Collection Lists.

In this latest version, support for form INPUTs ( textboxes ) has been added, using HTML5’s autocomplete features.

[View Demonstration in Webflow](https://sygnal-webflow-utils.webflow.io/demo/data-binding)

### How it Works <a href="#how-it-works" id="how-it-works"></a>

In SA, data-binding involves two steps;

1. Creating a JSON datasource using a Webflow Collection List.
2. Processing that JSON into HTML and linking it to the INPUTs and SELECTs you designate.

Setup is relatively simple, and you can use the Collection List’s built-in sorting and filtering options to precisely control the data you want in your Form controls.

### Getting Started <a href="#getting-started" id="getting-started"></a>

_Use the_ [_demo examples_](https://github.com/sygnaltech/webflow-util/tree/master/demo/webflow-forms/databinding) _as a current reference for using each feature._

**NOTE:** Here is a _outdated_ [video overview](https://www.youtube.com/watch?v=xc7vx7YdK5I) of setting up databinding in WFU v2.0. I’ll re-record soon. For now I’m leaving it as it will show you some of the internals on how the setup works.

#### STEP 1 - Add the Library <a href="#step-1---add-the-library" id="step-1---add-the-library"></a>

There are currently no configuration options for the data-binding feature, so we’ll use a _lo-code_ integration approach.

Paste this code, exactly, into the **Before `</body>` tag** script area of your Page settings. If you are using data-binding on multiple pages, you might choose to do this in your site-wide settings.

{% code overflow="wrap" %}
```html
<script type="module">
    import { dataBindAll } from 'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/locode/webflow-forms-helper.min.js';
    $(function () {
        dataBindAll();
    });
</script>
```
{% endcode %}

#### STEP 2 - Create a Collection List Data Source <a href="#step-2---create-a-collection-list-data-source" id="step-2---create-a-collection-list-data-source"></a>

First you need to setup your Collection List Data Source.

Follow the [instructions here](https://wfu.sygnal.com/docs/webflow-forms/databinding/datasources), and return to this document when you’ve completed.

This needs to be accessible on any page(s) that you’ll be doing data-binding, so if you’re

#### STEP 3 - Setup your Form <a href="#step-3---setup-your-form" id="step-3---setup-your-form"></a>

1. Now scroll to your form, and select the INPUT Textbox or SELECT List that you’re wanting to data-bind.
2. Add a custom attribute directly to that form control, with the name `wfu-bind`. This tells WFU that you want to bind this control to a datasource.
3. For the value, enter the data source name that you chose above.

NOTE: If you are binding a SELECT you may wish to remove the default values that Webflow has created. WFU will not delete them.

_You’re done._

To see data-binding in action, you’ll need to publish your site, and view the published results. Scripts won’t run in the Webflow designer.

## Troubleshooting <a href="#troubleshooting" id="troubleshooting"></a>

#### It’s not binding at all <a href="#its-not-binding-at-all" id="its-not-binding-at-all"></a>

If you’re not seeing anything in your dropdown when you open your SELECT, or when you click on your INPUT field, here are some things you can check;

* Double-check that you have the custom attribute `wfu-data` = (your data source name) on the outermost part of the Collection List.
* Double-check that you have the custom attribute `wfu-bind` = (your data source name) on the INPUT or SELECT that you’re wanting to data-bind.
* Double-check that your datasource name is exactly the same on both.
* Double-check that you have the script inserted in the right place in your page or site configuration.
* Make sure that your filter, sort, and item limit settings on your Collection List actually retrieve the data you want. If you need you can put a temporary text field and bind to that to double-check what items you’re pulling from your Collection. I recommend removing that test data before you publish to production.
* Run through the instructions above again and re-verify everything.

#### Something’s weird in the data on Form Posts <a href="#somethings-weird-in-the-data-on-form-posts" id="somethings-weird-in-the-data-on-form-posts"></a>

For INPUT elements, the value posted is whatever the user types in that textbox. Pretty simple.

For SELECTS, the value posted is the `id` you specified in your script block. Make sure you chose the right field for that, and that you have no extraneous spaces.

\
