# UTM Tracking

## What are UTM Params?&#x20;

UTM tracking data refers to Urchin Tracking Module parameters, which are a set of URL parameters used by marketers to track the effectiveness of online marketing campaigns across traffic sources and publishing media.&#x20;

UTM parameters are appended to URLs and provide detailed information about the source, medium, campaign, term, and content of the traffic coming to a website. This data is then used in web analytics tools like Google Analytics to analyze the performance of marketing efforts.

#### How UTM Parameters Work:

1. **Adding Parameters**: Marketers add UTM parameters to URLs used in their marketing campaigns.
2. **Tracking**: When a user clicks on a URL with UTM parameters, the parameters are sent to the destination website.
3. **Analytics**: Web analytics tools, such as Google Analytics, capture the UTM parameters and provide detailed reports on the traffic sources, mediums, campaigns, terms, and content.
4. **Analysis**: Marketers analyze this data to understand which campaigns are driving traffic, conversions, and other key performance indicators (KPIs).

#### Benefits of UTM Tracking:

* **Detailed Campaign Insights**: Gain insights into which campaigns are most effective in driving traffic and conversions.
* **Improved ROI**: Understand which marketing efforts provide the best return on investment.
* **Optimization**: Optimize future campaigns based on performance data.

By using UTM tracking, marketers can make data-driven decisions to improve the effectiveness of their marketing strategies.

The most common UTM parameters are:

1. **utm\_source**: Identifies the source of the traffic, such as a search engine (e.g., Google), newsletter, or other referring site.
   * Example: `utm_source=google`
2. **utm\_medium**: Identifies the medium of the traffic, such as email, CPC (cost-per-click), or organic search.
   * Example: `utm_medium=email`
3. **utm\_campaign**: Identifies the specific campaign that the traffic is associated with, such as a product launch or seasonal promotion.
   * Example: `utm_campaign=spring_sale`
4. **utm\_term**: Identifies the search terms used in paid search campaigns to generate the traffic (optional).
   * Example: `utm_term=running+shoes`
5. **utm\_content**: Differentiates between similar content or links within the same ad or campaign (optional).
   * Example: `utm_content=cta_button`

## Usage

SA5 lets you add UTM params to a URL automatically.  The purpose of making these individually controllable params is that they can be bound to CMS or component properties.&#x20;

`wfu-link-utm-source`

`wfu-link-utm-medium`

`wfu-link-utm-campaign`

`wfu-link-utm-content`





## Examples

[https://www.example.com/blog/article-title?utm\_source=email\&utm\_medium=share\&utm\_campaign=blog\_promotion\&utm\_content=article\_title\
](https://www.example.com/blog/article-title?utm\_source=email\&utm\_medium=share\&utm\_campaign=blog\_promotion\&utm\_content=article\_title)





