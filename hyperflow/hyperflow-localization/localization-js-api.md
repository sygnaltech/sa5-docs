# Localization JS API

Thanks Alex,

I do a similar thing in SA5's user info lib with the login/logout control to determine login state, which is also usually reflected in a cookie as well. I think as a hack I might use the hidden switcher approach, because one of the issues here is navigation.

Any time a script needs to navigate via Window.location.href, we have the problem of not knowing the correct path to route to. I think I might need to do this in two steps;

* Determine the current locale setting and store it in sessionstorage
* Redirect to the desired path, at the default locale path
* On that page have a script detect the sessionstorage value, determine the current locale, delete the sessionstorage key
* If the locales are different, then I find the hidden locale switcher, locate the coorec

Can I ask- I'm not seeing anything in webflow.js that I can access to determine any information, perform routing to a page, etc. Is there anything happening with graphql in the same way it does for users?
