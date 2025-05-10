# Triggers, Events & Actions 🧪

{% hint style="danger" %}
**NOT YET PUBLICLY AVAILABLE.**&#x20;
{% endhint %}

{% hint style="success" %}
**ABOUT TRIGGERS, EVENTS & ACTIONS** \
&#xNAN;_&#x46;unctional interactions_ is a new and currently developing facet of SA5. \
[Learn more](../../overview/events/). &#x20;
{% endhint %}

## Triggers &#x20;

### sa-trigger-tab-selected= ( _event name_ )&#x20;

Place on the tab itself

### sa-trigger-tab-changed = ( _event name_ )&#x20;

Place on the tabs element&#x20;

## Actions&#x20;

### sa-action-tab-change = ( _event name_ )&#x20;

#### sa-action-tab-change:tab

* Unsigned Integer 1, 2, 3 4, ...&#x20;
* Signed integer, + or -&#x20;
* Text name1, name2, name4, ...&#x20;



|    |                     |   |
| -- | ------------------- | - |
| 2  | Select the 2nd tab  |   |
| +1 | Select the next tab |   |
|    |                     |   |

#### sa-action-tab-change:loop = ( loop setting )&#x20;

Truthy&#x20;

<table><thead><tr><th width="131.66668701171875">Value </th><th>Behavior  </th><th>Notes </th></tr></thead><tbody><tr><td><code>true</code> </td><td>Loop in + and - operations </td><td>Only applies to signed positions that explicily</td></tr><tr><td><code>false</code> </td><td>Stop at the beginning or end </td><td></td></tr><tr><td></td><td></td><td></td></tr></tbody></table>



Tab index

Tab number

Tab



