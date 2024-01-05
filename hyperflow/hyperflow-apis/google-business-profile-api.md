# Google Business Profile API



## Use Cases

Opening hours;

* Open now? &#x20;
  * If near closing, for how much longer are they open?&#x20;
* Get opening hours directly from Google Maps so they can be displayed on the site with no need to update.
* Get holiday hours or special closures.&#x20;
  * When near term ( within N days ), make this available for a popup or special notice of some form.&#x20;

Reviews;

* Get reviews, display dynamically.&#x20;

Location;

* Nearest location, and driving directions, for phone users?&#x20;

## Technical Notes

* Caching
* Data-Present Triggers
* How to get Special Days for next 30 days ( instead of next 7 )&#x20;
* Google API key storage&#x20;

## ## Google Places API

[https://developers.google.com/maps/documentation/places/web-service/op-overview](https://developers.google.com/maps/documentation/places/web-service/op-overview)

Use the fields parameter to specify a comma-separated list of place data types to return. For example: `fields=formatted_address,name,geometry`. Use a forward slash when specifying compound values. For example: `opening_hours/open_now`.

Fields are divided into three billing categories: Basic, Contact, and Atmosphere. Basic fields are billed at base rate, and incur no additional charges. Contact and Atmosphere fields are billed at a higher rate. See the [pricing sheet](https://developers.google.com/maps/documentation/places/web-service/usage-and-billing/) for more information. Attributions, `html_attributions`, are always returned with every call, regardless of whether the field has been requested.

**Basic**

The Basic category includes the following fields: `address_components`, `adr_address`, `business_status`, `formatted_address`, `geometry`, `icon`, `icon_mask_base_uri`, `icon_background_color`, `name`, `permanently_closed` ([deprecated](https://developers.google.com/maps/deprecations)), `photo`, `place_id`, `plus_code`, `type`, `url`, `utc_offset`, `vicinity`, `wheelchair_accessible_entrance`.

**Contact**

The Contact category includes the following fields: `current_opening_hours`, `formatted_phone_number`, `international_phone_number`, `opening_hours`, `secondary_opening_hours`, `website`

**Atmosphere**

The Atmosphere category includes the following fields: `curbside_pickup`, `delivery`, `dine_in`, `editorial_summary`, `price_level`, `rating`, `reservable`, `reviews`, `serves_beer`, `serves_breakfast`, `serves_brunch`, `serves_dinner`, `serves_lunch`, `serves_vegetarian_food`, `serves_wine`, `takeout`, `user_ratings_total`.

## Setup

### Google Cloud API Key

[https://developers.google.com/maps/documentation/places/web-service/get-api-key](https://developers.google.com/maps/documentation/places/web-service/get-api-key)

[https://console.cloud.google.com/apis/library?pli=1](https://console.cloud.google.com/apis/library?pli=1)

### Config

Get your Place ID\
[https://developers.google.com/maps/documentation/javascript/examples/places-placeid-finder](https://developers.google.com/maps/documentation/javascript/examples/places-placeid-finder)

ChIJPyT9B61HDW0Rlme7V1GFBXU

```json
{
  "place_id": "YOUR PLACE ID",
  "api_key": "YOUR API KEY"
}
```

Worker Route, e.g.

\*hf.sygnal.com/api/google-places

## Research



[https://developers.google.com/maps/documentation/places/web-service/details#PlaceOpeningHours](https://developers.google.com/maps/documentation/places/web-service/details#PlaceOpeningHours)

[https://developers.google.com/my-business](https://developers.google.com/my-business)

[https://www.yext.com/knowledge-center/google-my-business-api](https://www.yext.com/knowledge-center/google-my-business-api)

