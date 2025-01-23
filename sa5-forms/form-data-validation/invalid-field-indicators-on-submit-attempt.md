# Invalid Field Indicators on Submit Attempt 🧪





Here's an example in which the invalid indicators only appear when the submit is attempted.&#x20;

* Invalid fields "shake"
  * And finish with a red outline&#x20;
*



## Attributes

{% hint style="info" %}
CONCEPTUAL.
{% endhint %}

wfu-form-validate-type = shake

on the form&#x20;



wfu-form-validate-field&#x20;

Used to identify a group







## Usage Notes

In general, the label and field need to be grouped so that they can "shake" together.&#x20;





## Example



```html

    <form id="sampleForm" novalidate>
      <div class="form-group">
        <label for="field1">Name (Required Text):</label>
        <input type="text" id="field1" name="field1" required>
      </div>
      <div class="form-group">
        <label for="field2">Email (Required Email):</label>
        <input type="email" id="field2" name="field2" pattern="[a-z]+@[a-z]+\.[a-z]{2,}" required>
      </div>
      <div class="form-group">
        <label for="field3">Code (Exactly Two Letters Required):</label>
        <input type="text" id="field3" name="field3" required pattern="^[A-Za-z]{2}$" placeholder="e.g., AB">
      </div>
      <div class="form-group">
        <label for="phone">Phone (US Format):</label>
        <input type="tel" id="phone" name="phone" required pattern="^\(?\d{3}\)?[-.\s]?\d{3}[-.\s]?\d{4}$" placeholder="e.g., 123-456-7890">
      </div>
      <button type="submit" id="submitButton">Submit</button>
    </form>
```







[https://codepen.io/memetican/pen/ByBqYJr/2911b074f1ed2bcff6885f29ea6d59f7](https://codepen.io/memetican/pen/ByBqYJr/2911b074f1ed2bcff6885f29ea6d59f7)

## Notes

Some field types like `tel` behave a bit differently;

* Special input on mobile devices&#x20;
* The `pattern` requirement is ignored or handled differently, it won't trigger validation&#x20;

We handle this as a secondary validation in SA5&#x20;





