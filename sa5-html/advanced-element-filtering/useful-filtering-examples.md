# Useful Filtering Examples

## Weekday or Weekend?

Show an element depending whether today is a weekday or weekend, _based on the user's local clock_.&#x20;

<table><thead><tr><th width="200"></th><th>wfu-filter-eval</th><th>wfu-filter-match</th></tr></thead><tbody><tr><td>Today is a Weekday </td><td><code>new Date().getDay() % 6 !== 0</code></td><td><code>[weekday='${(new Date().getDay() % 6 !== 0).toString()}'</code>]</td></tr><tr><td>Today is a Weekend </td><td><code>new Date().getDay() % 6 === 0</code></td><td><code>[weekday!='${(new Date().getDay() % 6 !== 0).toString()}'</code>]</td></tr></tbody></table>

{% hint style="info" %}
Both are untested.&#x20;
{% endhint %}



