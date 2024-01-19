# Hyperflow Layout Templates

## Goals

* Support item-specific layouts on a CMS page
* Make it easy to locate corresponding layouts and apply them



The only other approach that I'd use here is a reverse proxy, but in this case it's a rather complex setup. I'd build the layouts as un-indexable static pages e.g. `/layouts/layout-1` and it would contain the main arrangement of the page body, and determine what I want ( this grid, that gallery, a video... ).

You'd need to tag everything with custom attributes so that you can match them up, and then in your reverse proxy, it would get the layout, get your content, and act as a layout engine to combine them. This may require nodejs in order to really do the DOM manipulations you want.

