# Triggers, Events & Actions 🧪



{% hint style="danger" %}
**NOT YET PUBLICLY AVAILABLE.**&#x20;
{% endhint %}

{% hint style="success" %}
**ABOUT TRIGGERS, EVENTS & ACTIONS** \
&#xNAN;_&#x46;unctional interactions_ is a new and currently developing facet of SA5. \
[Learn more](../../overview/events/). &#x20;
{% endhint %}

## Triggers&#x20;

### sa-trigger-accordion-changed

Place on the slider if you want all slide changes to trigger the Event.&#x20;

Place on an individual slide if you want only changing to that sclie

Place on the slide element&#x20;

### sa-trigger-accordion-focus



### sa-trigger-accordion-blur



## Actions&#x20;

### sa-action-accordion-change

#### sa-action-slide-change:tab

* Unsigned Integer 1, 2, 3 4, ...&#x20;
* Signed integer, + or -&#x20;
* Text name1, name2, name4, ...&#x20;



|    |                       |   |
| -- | --------------------- | - |
| 2  | Select the 2nd slide  |   |
| +1 | Select the next slide |   |
|    |                       |   |

#### sa-action-slide-change:loop = ( loop setting )&#x20;

Truthy&#x20;

<table><thead><tr><th width="131.66668701171875">Value </th><th>Behavior  </th><th>Notes </th></tr></thead><tbody><tr><td><code>true</code> </td><td>Loop in + and - operations </td><td>Only applies to signed positions that explicily</td></tr><tr><td><code>false</code> </td><td>Stop at the beginning or end </td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>



Slide index

Slide number

Slide name&#x20;



