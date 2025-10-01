# Pretty Pagination Querystring



Webflow's collection list pagination adds URL querystrings like this;

```
?6801a15e_page=2
```

While these are important, they're not especially attractive and some clients prefer a code-free appearance like;

```
?page=2
```

_This is not natively supported by Webflow._&#x20;

The reason the code exists is to identify which page you're on for _each_ collection list, up to 20.  Therefore to differentiate them, the code is important and you may have several;

```
?6801a15e_page=2&?8801e222_page=8?25401a12f_page=12
```

{% hint style="warning" %}
It would be nice to be able to designate a single primary collection list for the page, and have that only form a cleaner no-ID querystring. However this is not currently a Webflow feature.&#x20;
{% endhint %}

## A Hack&#x20;

If you don't mind a flicker, you can hide that coded param using client-side JS.&#x20;

1. Place in the before-/head custom code area of the specific page you want this on.
2. Edit the `REAL_PARAM` at the top to indicate the actual querystring param.&#x20;

```html
<script>
(() => {
  const REAL_PARAM = '6801a15e_page'; // <-- your Webflow param
  const FRIENDLY   = 'page';

  const url = new URL(location.href);
  const s = url.searchParams;

  // Friendly -> real (reload once so Webflow serves correct page)
  if (s.has(FRIENDLY) && !s.has(REAL_PARAM)) {
    const v = s.get(FRIENDLY);
    if (/^\d+$/.test(v) && +v >= 1) {
      s.set(REAL_PARAM, v);
      s.delete(FRIENDLY);
      location.replace(url.toString());
      return;
    }
  }

  // Real -> friendly (address bar only; no reload)
  if (s.has(REAL_PARAM) && !s.has(FRIENDLY)) {
    const v = s.get(REAL_PARAM);
    if (/^\d+$/.test(v)) {
      const friendly = new URL(url);
      friendly.searchParams.set(FRIENDLY, v);
      friendly.searchParams.delete(REAL_PARAM);
      history.replaceState(null, '', friendly.toString());
    }
  }

  // Optional: make links using ?page=N go straight to the real param (no extra round-trip)
  addEventListener('click', (e) => {
    const a = e.target && e.target.closest && e.target.closest('a[href]');
    if (!a) return;
    const u = new URL(a.href, location.origin);
    if (u.pathname === location.pathname && u.searchParams.has(FRIENDLY) && !u.searchParams.has(REAL_PARAM)) {
      const v = u.searchParams.get(FRIENDLY);
      if (/^\d+$/.test(v) && +v >= 1) {
        u.searchParams.set(REAL_PARAM, v);
        u.searchParams.delete(FRIENDLY);
        e.preventDefault();
        location.href = u.toString();
      }
    }
  }, { capture: true });
})();
</script>

```









