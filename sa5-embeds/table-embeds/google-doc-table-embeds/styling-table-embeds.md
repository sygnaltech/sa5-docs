# Styling Table Embeds

SA5 has a default theme you can use as a starting point.

To create your own theme, you can;

* Copy this code into an embed&#x20;
* Set your theme attribute to `wfu-theme` = `custom`
* Modify the code to your liking, as you would any other custom CSS&#x20;

{% hint style="success" %}
If you build something elegant you think the SA5 community would benefit from, let us know!  We may include additional community-created themes in the library.&#x20;
{% endhint %}

```html
<style>
[wfu-theme=custom] table {
  border-collapse: collapse;
  margin-top: 10px;
}
[wfu-theme=custom] table tr td {
  padding: 0.2rem 1rem;
  border: 1px solid white;
  vertical-align: top;
  margin-bottom: 5px;
}
[wfu-theme=custom] table tr td p {
  line-height: 22px;
  font-size: 14px;
}
[wfu-theme=custom] table tr td ul {
  padding-left: 5px;
  padding-top: 10px;
  padding-bottom: 0.2rem;
}
[wfu-theme=custom] table tr td ul li::marker {
  content: "⁃";
  color: #2e9dff;
}
[wfu-theme=custom] table tr td ul li {
  line-height: 22px;
  font-size: 14px;
  padding-left: 1ch;
}
[wfu-theme=custom] table tr:nth-child(1) {
  font-weight: 800;
  background-color: rgba(255, 255, 255, 0.2);
} 
</style> 
```













