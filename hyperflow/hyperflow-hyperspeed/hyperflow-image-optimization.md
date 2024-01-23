# Hyperflow Image Optimization

## Goals

* Optimize all images
  * HTML Images ( src )
  * HTML Media sercset images ( srcset )
  * Background Images
* Domain consistency for SEO&#x20;
* Edge-cache non-optimized images
* Minimal monthly hosting costs for optimization and caching

## Features

### Coverage

|            | Present                                   | Future                                                                         |
| ---------- | ----------------------------------------- | ------------------------------------------------------------------------------ |
| Coverage   |                                           | CSS Background Images                                                          |
| Asset URLs | `https://assets-global.website-files.com` | <ul><li><code>https://assets.website-files.com</code></li><li>Others</li></ul> |
|            |                                           |                                                                                |

### Options

|                         |              |                                             |
| ----------------------- | ------------ | ------------------------------------------- |
| Multiple configurations |              | <p>Applied by;<br>- Custom attributes</p>   |
| Ignore image            |              | <ul><li>No proxy, no optimization</li></ul> |
| Quality                 | Fixed at 90% |                                             |
| Transform types         | Auto         | <ul><li>From and to types</li></ul>         |

* Images
  * Automatically detect and optimize all HTML-referenced images on the site
    * HTML Images ( `src` )
    * HTML Media srcset images ( `srcset` )
  * Configure the from and to formats
    * e.g. which to WEBP convert, which not to for animation purposes&#x20;

## Future

* Proxy other image types like PDF
* Possibly optimize them&#x20;
* CSS-referenced images such as background images&#x20;
* Ability to zone and classify image rules;
  * By page
  * Page section ( attributes )
  * Custom attributes override directly on image&#x20;
  * &#x20;



`https://assets-global.website-files.com`

`https://assets.website-files.com`



\`HTML Images ( `src=` )

HTML Media srcset images ( `srcset=` )

CSS background images





Future



alt domains

user images?&#x20;

uploaded images?&#x20;













## Configurations

### &#x20;<a href="#enable-transformations" id="enable-transformations"></a>

\


## Cassette

assets.sygnal.com

[https://1assets-global.website-files.com](https://1assets-global.website-files.com)

