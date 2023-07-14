# Payment Providers

Webflow has an in-build e-commerce solution, however it adds a substantial monthly cost and lacks some capabilities. Sometimes you just need something simple, and crude, and cheap.

Fortunately, there are some payment providers who can be easily integrated using a simple payment URL format.

This library allows you to easily construct those URLs.

Currently we support two providers-

* Windcave
* Paypal

Important- this is not a no-code solution. It simply encapsulates the URL construction.

## Getting Started ( NOCODE ) <a href="#getting-started-nocode" id="getting-started-nocode"></a>

### STEP 1 - Write your Code <a href="#step-1---write-your-code" id="step-1---write-your-code"></a>

e.g.;

{% code overflow="wrap" %}
```html
<script type="module">
import { WindcavePayment, PaypalPayment } from "https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/modules/webflow-commerce.min.js";

$(function() {
  
    var payPaypal = new PaypalPayment();
    payPaypal.business = "pay@sygnal.com"; // your Paypal email
    payPaypal.amount = totalWithFees; // the numeric total amount
    payPaypal.currency_code = "NZD"; // currency you want
    payPaypal.item_name = orderDescription; // what was ordered
    
    // Set this URL on your payment link 
    $("#btn-pay-paypal").attr("href", payPaypal.generateUrl());

});
</script>
```
{% endcode %}

\
