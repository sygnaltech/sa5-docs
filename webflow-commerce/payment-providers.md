---
description: Simple payment-link tools
---

# Payment Providers

{% hint style="info" %}
The tools here are not related to Webflow's native ECommerce platform. They are simple payment link tools to provide crude payment capability through services like Paypal and Windcave.&#x20;
{% endhint %}

Currently we support two providers-

* Windcave
* Paypal

## Usage Notes | Windcave

{% embed url="https://www.windcave.com/developer-ecommerce-payform" %}

### Demonstration

{% embed url="https://codepen.io/memetican/pen/oNQVEOK/22f9b91499d51f57f2ed1be29c29d9a6" %}
Windcave example
{% endembed %}

### Windcave Example <a href="#step-1---write-your-code" id="step-1---write-your-code"></a>

{% code overflow="wrap" %}
```html
<script src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.20/dist/webflow-commerce.js"></script>

<script>
    var payment = new window.sa5.WindcavePayment();

    // Configure the payment link
    payment.userid = 'user id';
    payment.amount = '10.00';
    payment.currencyname = 'USD';
    payment.txndata1 = '';
    payment.txndata2 = '';
    payment.txndata3 = '';
    payment.email = 'email@foo.bar';

    // Do something with the payment link
    console.log(payment.generateUrl());
</script>
```
{% endcode %}

## Usage Notes | PayPal

### PayPal Example

{% code overflow="wrap" %}
```html
<script src="https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@5.2.20/dist/webflow-commerce.js"></script>

<script>
    var payment = new window.sa5.PaypalPayment();

    // Configure the payment link
    payment.business = 'user id';
    payment.amount = '10.00';
    payment.currencyname = 'USD';
    payment.item_name = 'widget';

    // Do something with the payment link
    console.log(payment.generateUrl());
</script>

```
{% endcode %}
