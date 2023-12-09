# Locale Switcher & Flags

[https://university.webflow.com/lesson/build-a-locale-switcher?topics=localization](https://university.webflow.com/lesson/build-a-locale-switcher?topics=localization)

[https://university.webflow.com/lesson/localization-overview?topics=localization](https://university.webflow.com/lesson/localization-overview?topics=localization)

[https://docs.developers.webflow.com/docs/working-with-localization](https://docs.developers.webflow.com/docs/working-with-localization)

[https://university.webflow.com/lesson/localized-seo-and-locale-routing?topics=localization](https://university.webflow.com/lesson/localized-seo-and-locale-routing?topics=localization)

[https://university.webflow.com/lesson/localize-collection-content?topics=localization](https://university.webflow.com/lesson/localize-collection-content?topics=localization)



Goals;&#x20;

* Add flags
* Add localized name&#x20;
* Allow ordering

Possibly;&#x20;

* Auto-routing&#x20;





Flags



Localized language name&#x20;



ISO 639-1 codes are two-letter codes used to represent languages. Here are several examples, each representing a different language:



## Challenges-

* Main flag
  * Update on load
  * Update on change
    * Identify change event&#x20;
* Menu flags
  * Update on load





Webflow issues an ISO&#x20;

English: en Spanish: es French: fr German: de Chinese: zh Japanese: ja Russian: ru Arabic: ar Portuguese: pt Italian: it Korean: ko Dutch: nl Swedish: sv Danish: da Polish: pl Norwegian: no Hindi: hi Greek: el Turkish: tr Hebrew: he

Notes

langcode - [http://www.lingoes.net/en/translator/langcode.htm](http://www.lingoes.net/en/translator/langcode.htm)



Art sources&#x20;

[https://cdn.jsdelivr.net/gh/lipis/flag-icons@main/flags/1x1/cn.svg\
](https://cdn.jsdelivr.net/gh/lipis/flag-icons@main/flags/1x1/cn.svg)

[https://github.com/lipis/flag-icons/blob/main/flags/1x1/cn.svg](https://github.com/lipis/flag-icons/blob/main/flags/1x1/cn.svg)

[https://github.com/lipis/flag-icons/tree/main/flags/1x1](https://github.com/lipis/flag-icons/tree/main/flags/1x1)

[https://github.com/lipis/flag-icons](https://github.com/lipis/flag-icons)

Detailed - [https://flagicons.lipis.dev/](https://flagicons.lipis.dev/)

[https://snzi.netlify.app/zh.svg](https://snzi.netlify.app/zh.svg)

[https://pub.dev/documentation/country\_flags/latest/](https://pub.dev/documentation/country\_flags/latest/)

[https://flagsapi.com/](https://flagsapi.com/)

Nice quality, but variable aspect ratios for a few;&#x20;

[https://github.com/JeremyPersing/countryflagsapi](https://github.com/JeremyPersing/countryflagsapi)

flags - [https://github.com/sygnaltech/webflow-flags/tree/stable](https://github.com/sygnaltech/webflow-flags/tree/stable)

## Referencing

{% hint style="info" %}
Both language codes, and language-locale codes can be in the same dir.&#x20;
{% endhint %}

ISO 639-1 language codes and ISO 3166-1 alpha-2 country codes are designed to be distinct from one another to avoid confusion. The ISO (International Organization for Standardization) ensures that the codes in these two different standards do not overlap. ISO 639-1 codes are used to represent languages (like 'en' for English, 'es' for Spanish), while ISO 3166-1 alpha-2 codes are used for country names (like 'US' for the United States, 'FR' for France).

Here are a few key points to understand:

1. **Different Standards**: ISO 639-1 and ISO 3166-1 alpha-2 are separate standards maintained by different ISO committees, specifically designed for different purposes.
2. **No Overlap by Design**: The codes are carefully chosen to avoid any overlap. The organizations responsible for these standards are aware of the potential for confusion and work to prevent it.
3. **Distinct Purposes**: The separation of these standards also reflects their distinct uses – language codes are used to identify languages, while country codes are used in various contexts like domain names, postal addressing, and international shipping.

In conclusion, there is no overlap or conflict between the two-digit ISO language codes and the two-digit ISO country codes, ensuring clarity and distinct identification in international contexts.
