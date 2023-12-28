---
description: Advanced CSS Optimizations for Webflow
---

# Hyperflow CSS

## Concept

* Optimize CSS
  * Remove unused CSS
    * Per page?

## Tech&#x20;

PurgeCSS: This tool removes unused CSS. It can be configured to consider various file types that might reference your CSS classes (HTML, JS, Vue, etc.). By scanning your files, it creates a minimized CSS file that only includes the styles actually used on your site.

UnCSS: Similar to PurgeCSS, UnCSS analyzes your HTML files and removes unused styles from your stylesheet. It works well with single-page apps and static sites.

csso: CSSO (CSS Optimizer) is a CSS minifier that also performs structural optimization of CSS files, merging duplicated selectors and declarations.

Clean-CSS: This is a fast and efficient library available as a Node.js module. It minifies CSS, removes duplicates, and restructures your CSS file for better utilization.

PostCSS: PostCSS is a tool for transforming CSS with JavaScript plugins. These plugins can lint your CSS, support variables and mixins, transpile future CSS syntax, inline images, and more. The postcss-merge-rules plugin, for instance, can merge duplicate CSS rules.

Responsive Breakpoints: Use tools like sass-mq or postcss-media-minmax to manage your media queries more efficiently. These can help you define your breakpoints in a single place and keep them organized.

Critical: Extracts & inlines critical-path (above-the-fold) CSS from HTML. This can be used to deliver a minimal amount of style while a separate asynchronous task loads the rest of the stylesheets.

### Mobile Optimization

When you're targeting mobile devices specifically, you can take these additional steps:

* Use Media Query Splitting: Some build tools can split your CSS based on media queries. For instance, with webpack, you can use media-query-plugin to split your CSS into separate files and then load them conditionally.
* Media Query Handling: Ensure that your CSS only contains media queries relevant for mobile devices. You can manually remove media queries that target desktop-specific layouts or use a tool that automatically strips out non-mobile queries.
* Automation Tools: You can create a build process using task runners like Gulp or Grunt with a series of these tools to automate CSS optimization.
* Custom Cloudflare Workers: As mentioned in a previous answer, a Cloudflare Worker can be written to serve different CSS files based on the User-Agent header, ensuring that only mobile-relevant CSS is delivered to mobile devices.

## Notes

\
WORKER\
addEventListener('fetch', event => {  event.respondWith(handleRequest(event.request));});\
async function handleRequest(request) {  // Extract the page identifier from the request, e.g., by parsing the referrer or URL  const pageIdentifier = ...;\
&#x20; // Map the page identifier to the corresponding CSS file  const cssFileName = ...;\
&#x20; // Fetch the CSS file from your server or storage  const cssFileUrl = \`[https://yourserver.com/path/to/css/](https://yourserver.com/path/to/css/)${cssFileName}\`;  const cssResponse = await fetch(cssFileUrl);\
&#x20; // Clone the response so you can modify the headers  const response = new Response(cssResponse.body, cssResponse);\
&#x20; // Set caching headers  response.headers.set('Cache-Control', 'public, max-age=31536000');\
&#x20; return response;}

\
\
PURGECSS\
Export from Webflow:

* Navigate to your Webflow dashboard.
* Go to your project settings and find the 'Export' option.
* Export your site, which will download a .zip file containing your HTML, CSS, and other assets.

Set Up PurgeCSS:

* You'll need Node.js installed on your computer. If you haven't installed it yet, you can download it from the [official Node.js website](https://nodejs.org/).
* Install PurgeCSS globally via npm (Node Package Manager) by running npm install -g purgecss in your terminal or command prompt.

Run PurgeCSS:

* Unzip the exported files from Webflow into a folder on your computer.
* Open a terminal or command prompt and navigate to the folder where you've unzipped your Webflow export.
* Run PurgeCSS with a command like the following:

\
\
purgecss --css path/to/cssfile.css --content path/to/index.html --output path/to/outputfolder

