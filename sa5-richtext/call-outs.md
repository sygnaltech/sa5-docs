---
description: Convert any Webflow blockquote to a stylized callout
---

# Call-Outs

Convert any Webflow blockquote to a stylized callout including an icon, font and background color

* **Information**: ℹ️ (Information Symbol)
* **Warning**: ⚠️ (Warning Symbol)
* **Success**: ✅ (Check Mark)
* **Caution**: ⚠️ (Triangle Warning)
* **Error**: ❌ (Cross Mark)
* **Note**: 📝 (Memo)&#x20;
* **Tips**: 💡 (Light Bulb)
* **FAQs**: ❓ (Question Mark)
* **Quotes**: 🗣️ (Speaking Head)



## Recommended Icons

Default

Custom



Styling by color

Create classes

( paste from cloneable )&#x20;

`.sa5-callout-info`&#x20;

Background color, image, side border&#x20;

, background icon&#x20;

font, etc.&#x20;



border-levt



Prefixes;&#x20;



|            |      | Default styling  |
| ---------- | ---- | ---------------- |
| `/info`    | `i`  | Info. Blue.      |
| `/warning` | `!!` | Danger. Red.     |
| `/caution` | `!`  | Caution. Orange. |
| `/note`    |      |                  |
| `/faq`     | `?`  |                  |
| `/feature` |      | Success. Green.  |
|            |      | Yellow           |
|            |      | Purple           |



Optional first line of text, e.g. "did you know?"&#x20;

Control with CSS and `::before` styling&#x20;



* **Information**: `i`
* **Warning**: `!`
* **Success**: `+`
* **Caution**: `*`
* **Error**: `x`
* **Note**: `n`



[https://codepen.io/memetican/pen/BaeJPwY/6eb9010c97458d0c708ac20b44fb2c39](https://codepen.io/memetican/pen/BaeJPwY/6eb9010c97458d0c708ac20b44fb2c39)

[https://codepen.io/memetican/pen/abrqvpe/17a1a0ec34b7dbfa470b32a4d80ec090](https://codepen.io/memetican/pen/abrqvpe/17a1a0ec34b7dbfa470b32a4d80ec090)









```
blockquote.callout {
    padding: 1em;
    margin: 1em 0;
    border-radius: 5px;
    position: relative;
    padding-left: 2em;
    font-style: italic;
}

.callout-info {
    background-color: #e7f3fe;
    border-left: 5px solid #2196F3;
}

.callout-warning {
    background-color: #fff3cd;
    border-left: 5px solid #ffc107;
}

.callout-success {
    background-color: #d4edda;
    border-left: 5px solid #28a745;
}

.callout-error {
    background-color: #f8d7da;
    border-left: 5px solid #dc3545;
}

.callout-note {
    background-color: #e2e3e5;
    border-left: 5px solid #6c757d;
}

.callout-icon {
    position: absolute;
    left: 10px;
    top: 10px;
    font-size: 1.5em;
}

```

```
document.querySelectorAll('blockquote.callout').forEach(blockquote => {
    const text = blockquote.textContent.trim();
    let icon = '';
    let typeClass = '';

    if (text.startsWith('ℹ️')) {
        typeClass = 'callout-info';
        icon = 'ℹ️';
    } else if (text.startsWith('⚠️')) {
        typeClass = 'callout-warning';
        icon = '⚠️';
    } else if (text.startsWith('✅')) {
        typeClass = 'callout-success';
        icon = '✅';
    } else if (text.startsWith('❌')) {
        typeClass = 'callout-error';
        icon = '❌';
    } else if (text.startsWith('📝')) {
        typeClass = 'callout-note';
        icon = '📝';
    }

    if (typeClass) {
        blockquote.classList.add(typeClass);
        blockquote.innerHTML = `<span class="callout-icon">${icon}</span>` + blockquote.innerHTML.slice(icon.length);
    }
});

```









