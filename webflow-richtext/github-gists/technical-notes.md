# Technical Notes

## Configuration



* Maxheight feature, where scrolling happens

## Copy Gists

Copy feature from raw.&#x20;

## Styling Gists

Custom themes&#x20;

{% hint style="danger" %}
These are experimental approaches.
{% endhint %}

Gists are embedded using a JS script which generates the formatted Gist content. It is not IFRAME'd which means it can be accessed directly via CSS.

However it is also undocumented styling.

[https://codersblock.com/blog/customizing-github-gists/](https://codersblock.com/blog/customizing-github-gists/)

Themes and styling;

[https://github.com/StylishThemes/GitHub-Dark/blob/master/src/themes/github/one-dark.css](https://github.com/StylishThemes/GitHub-Dark/blob/master/src/themes/github/one-dark.css)

## Themes

[https://danielbernal.co/styling-gist-embeds-with-css/](https://danielbernal.co/styling-gist-embeds-with-css/)

[https://stylishthemes.github.io/GitHub-Dark/](https://stylishthemes.github.io/GitHub-Dark/)

[https://github.com/StylishThemes](https://github.com/StylishThemes)

[https://github.com/StylishThemes/GitHub-Dark#available-syntax-highlighting-themes-demo](https://github.com/StylishThemes/GitHub-Dark#available-syntax-highlighting-themes-demo)

## Raw Retrieve & Format

Raw retrieval;&#x20;

```
https://gist.github.com/raw/[ID]/[REVISION]/[FILE]
```

or

```
https://gist.githubusercontent.com/raw/[ID]/[REVISION]/[FILE]
```

`[ID]` is necessary\
`[REVISION]` can be omitted to get the latest revision\
`[FILE]` can be omitted to get the first file

[https://gist.github.com/atenni/5604615](https://gist.github.com/atenni/5604615)

{% embed url="https://gist.githubusercontent.com/memetican/ca27982d01fbe65127da7e22104fab71/raw" %}

Or it can be retrieved via GitHub's Gist API.&#x20;

#### To get Gist Data;

[https://api.github.com/gists/8a6a3c508b7c71deb4070d3314900b1f](https://api.github.com/gists/8a6a3c508b7c71deb4070d3314900b1f)

{% embed url="https://gist.github.com/atenni/5604615" %}

[https://raw.githack.com/](https://raw.githack.com/)

[https://docsify.js.org/#/embed-files?id=embed-a-gist](https://docsify.js.org/#/embed-files?id=embed-a-gist)

[https://stackoverflow.com/questions/46073096/is-there-a-permalink-to-the-latest-version-of-gist-files](https://stackoverflow.com/questions/46073096/is-there-a-permalink-to-the-latest-version-of-gist-files)

[https://stackoverflow.com/questions/16589511/how-do-i-get-the-raw-version-of-a-gist-from-github](https://stackoverflow.com/questions/16589511/how-do-i-get-the-raw-version-of-a-gist-from-github)

####
