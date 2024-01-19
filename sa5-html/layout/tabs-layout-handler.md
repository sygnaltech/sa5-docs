# Tabs Layout Handler



<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

wfu-tabs = NAME

wfu-tabs-init = clear

wfu-tabs-move = TARGET-NAME

wfu-tabs-name = TEXT&#x20;



{% hint style="info" %}
This is the most basic Tabs rendition created, before webflow.js has initialized it.&#x20;
{% endhint %}

{% code overflow="wrap" %}
```html
<div wfu-tabs-target="_main" data-current="Tab 1" data-easing="ease" data-duration-in="300" data-duration-out="100" class="w-tabs">
   <div class="w-tab-menu">
      <a data-w-tab="Tab 1" class="w-inline-block w-tab-link w--current">
         <div>Tab 1</div>
      </a>
      <a data-w-tab="Tab 2" class="w-inline-block w-tab-link">
         <div>Tab 2</div>
      </a>
      <a data-w-tab="Tab 3" class="w-inline-block w-tab-link">
         <div>Tab 3</div>
      </a>
   </div>
   <div class="w-tab-content">
      <div data-w-tab="Tab 1" class="w-tab-pane w--tab-active"></div>
      <div data-w-tab="Tab 2" class="w-tab-pane"></div>
      <div data-w-tab="Tab 3" class="w-tab-pane"></div>
   </div>
</div>
```
{% endcode %}







{% code overflow="wrap" %}
```html
// Some code
<div wfu-tabs-target="_main" data-current="Tab 1" data-easing="ease" data-duration-in="300" data-duration-out="100" class="w-tabs">
   <div class="w-tab-menu" role="tablist">
      <a data-w-tab="Tab 1" class="w-inline-block w-tab-link w--current" id="w-tabs-0-data-w-tab-0" href="#w-tabs-0-data-w-pane-0" role="tab" aria-controls="w-tabs-0-data-w-pane-0" aria-selected="true">
         <div>Tab 1</div>
      </a>
      <a data-w-tab="Tab 2" class="w-inline-block w-tab-link" tabindex="-1" id="w-tabs-0-data-w-tab-1" href="#w-tabs-0-data-w-pane-1" role="tab" aria-controls="w-tabs-0-data-w-pane-1" aria-selected="false">
         <div>Tab 2</div>
      </a>
      <a data-w-tab="Tab 3" class="w-inline-block w-tab-link" tabindex="-1" id="w-tabs-0-data-w-tab-2" href="#w-tabs-0-data-w-pane-2" role="tab" aria-controls="w-tabs-0-data-w-pane-2" aria-selected="false">
         <div>Tab 3</div>
      </a>
   </div>
   <div class="w-tab-content">
      <div data-w-tab="Tab 1" class="w-tab-pane w--tab-active" id="w-tabs-0-data-w-pane-0" role="tabpanel" aria-labelledby="w-tabs-0-data-w-tab-0"></div>
      <div data-w-tab="Tab 2" class="w-tab-pane" id="w-tabs-0-data-w-pane-1" role="tabpanel" aria-labelledby="w-tabs-0-data-w-tab-1"></div>
      <div data-w-tab="Tab 3" class="w-tab-pane" id="w-tabs-0-data-w-pane-2" role="tabpanel" aria-labelledby="w-tabs-0-data-w-tab-2"></div>
   </div>
</div>
```
{% endcode %}







{% code overflow="wrap" %}
```
// Some code
<div wfu-tabs-target="_main" data-current="Tab 1" data-easing="ease" data-duration-in="300" data-duration-out="100" class="w-tabs">
   <div class="w-tab-menu" role="tablist">
      <a data-w-tab="Tab 1" class="w-inline-block w-tab-link w--current" id="w-tabs-0-data-w-tab-0" href="#w-tabs-0-data-w-pane-0" role="tab" aria-controls="w-tabs-0-data-w-pane-0" aria-selected="true">
         <div>Tab 1</div>
      </a>
      <a data-w-tab="Tab 2" class="w-inline-block w-tab-link" tabindex="-1" id="w-tabs-0-data-w-tab-1" href="#w-tabs-0-data-w-pane-1" role="tab" aria-controls="w-tabs-0-data-w-pane-1" aria-selected="false">
         <div>Tab 2</div>
      </a>
      <a data-w-tab="Tab 3" class="w-inline-block w-tab-link" tabindex="-1" id="w-tabs-0-data-w-tab-2" href="#w-tabs-0-data-w-pane-2" role="tab" aria-controls="w-tabs-0-data-w-pane-2" aria-selected="false">
         <div>Tab 3</div>
      </a>
   </div>
   <div class="w-tab-content">
      <div data-w-tab="Tab 1" class="w-tab-pane w--tab-active" id="w-tabs-0-data-w-pane-0" role="tabpanel" aria-labelledby="w-tabs-0-data-w-tab-0"></div>
      <div data-w-tab="Tab 2" class="w-tab-pane" id="w-tabs-0-data-w-pane-1" role="tabpanel" aria-labelledby="w-tabs-0-data-w-tab-1"></div>
      <div data-w-tab="Tab 3" class="w-tab-pane" id="w-tabs-0-data-w-pane-2" role="tabpanel" aria-labelledby="w-tabs-0-data-w-tab-2"></div>
   </div>
</div>
```
{% endcode %}

