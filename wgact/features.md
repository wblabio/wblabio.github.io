# Highlights

- Tracking Pixels
 
 The plugin provides a variety of the most common tracking pixels for e-commerce such as Google Ads, Google Analytics, Facebook, Microsoft Ads and more. 

 You can use just one, or a selection of tracking pixels that suite your own purpose best.

 The plugin covers all of the core features that each pixel provides. Beta features are on the development roadmap and will be implemented soon. 
 
- Powerful control layer, yet simple to use
 
 The design principles for the plugin are simplicity and accuracy. That means we designed the user interface to be very simple to use. At the same time we pay a lot of attention to the logic beneath the surface to make the tracking pixels work as accurate as technically possible. 

 The plugin's powerful, internal pixel manager controls all the pixels and their settings, while making it very easy for the user to adjust the behavior globally.  

 Wherever possible, the internal pixel manager automatically detects the best settings for the specific environment which allows to keep the user interface uncluttered and as light as possible. 

 And, the plugin is very developer friendly. It provides hooks and filters to enable users to adjust the plugin behavior in ways that we didn't think of. 

- Privacy features

 Privacy concerns and new regulation have driven a development of many new Consent Management Platforms (CMPs). At the same time the pixel providers (like Google and Facebook) have implemented new features into their tracking pixels that give the website visitors much more control over the data collected. 

 The plugin integrates seamlessly with the most popular Consent Management Platforms and implements all of the new tracking pixel privacy features available to date.

## Pro Features Principles

When we decide to include a feature into the Pro version rather than the Free version there are several considerations we make. Following we'll explain a few of the principles: 

- New features (like beta features) will only become available for users of the Pro version.
- If a new feature is essential for the working of the free version we will make it available to the users of the free version as soon as possible. 
- Complex features that generate a high volume of support requests will only be available for users of the Pro version. 
- The subscriptions for the Pro version must cover the costs for giving support and further improving the plugin (for the Pro version and the Free version). 

## Features

### Pixels

Pixel                                             | free | pro
---                                               | ---  | ---
**Facebook**                                      | ✔️    | ✔️
**Google Universal Analytics**                    | ✔️    | ✔️
**Google Analytics 4**                            | ✔️    | ✔️
**Google Ads**                                    | ✔️    | ✔️
**Google Optimize**                               | ✔️    | ✔️
**Hotjar**                                        | ✔️    | ✔️
**Microsoft Ads**                                 |      | ✔️
**Twitter Ads**                                   |      | ✔️
**Pinterest Ads**                                 |      | ✔️


### General Features

The following features are implemented in all pixels (as long as the specific pixel supports that type of feature).

Feature                                           | free | pro
---                                               | ---  | ---
**Purchase transaction ID**                       | ✔️    | ✔️
**Purchase currency**                             | ✔️    | ✔️
**Basic order deduplication**                     | ✔️    | ✔️
**Advanced order deduplication**                  |      | ✔️
**Ignore orders where the payment failed**        | ✔️    | ✔️
**Different Types of Order Total Calculation**    | ✔️    | ✔️
**Localized by professional translators**         | ✔️    | ✔️
**Environment checks**                            | ✔️    | ✔️
**Event processing on lazy loaded products**      | ✔️    | ✔️
**Compatibility modes for various JavaScript optimizers**  | ✔️    | ✔️
**Custom conversions with shortcodes**            | ✔️    | ✔️
**Conversion value filter for custom order total calculation** | ✔️    | ✔️


### Google 

Feature                                           | free | pro
---                                               | ---  | ---
**Consent mode**                                  |      | ✔️
**Cross domain linker**                           | ✔️    | ✔️
**Cookiebot settings for Google consent mode**    |      | ✔️
**User ID tracking**                              |      | ✔️


### Google Analytics

Feature                                           | free | pro
---                                               | ---  | ---
**Standard e-commerce tracking**                  | ✔️    | ✔️
**Enhanced e-commerce tracking**                  |      | ✔️
**Enhanced link attribution**                     | ✔️    | ✔️
**Product item data**                             | ✔️    | ✔️


### Google Ads

Feature                                               | free | pro
---                                                   | ---  | ---
**Conversion tracking**                               | ✔️    | ✔️
**All dynamic remarketing events**                    | ✔️    | ✔️
**Cart item tracking**                                | ✔️    | ✔️
**Retail business vertical**                          | ✔️    | ✔️
**All business verticals**                            |      | ✔️
**Add multiple conversion pixels (filter)**           | ✔️    | ✔️
**Phone conversion tracking**                         |      | ✔️
**Purchase transaction ID**                           | ✔️    | ✔️
**Purchase currency**                                 | ✔️    | ✔️


### Facebook 

Feature                                           | free | pro
---                                               | ---  | ---
**All dynamic remarketing events**                | ✔️    | ✔️
**Facebook product microdata output**             |      | ✔️
**Conversion API (CAPI)**                         |      | ✔️
**Purchase transaction ID**                       | ✔️    | ✔️
**Purchase currency**                             | ✔️    | ✔️


### Microsoft Ads

Feature                                           | free | pro
---                                               | ---  | ---
**Purchase event tracking**                       |      | ✔️
**All dynamic remarketing events**                |      | ✔️
**Purchase currency**                             | ✔️    | ✔️

### Twitter Ads

Feature                                           | free | pro
---                                               | ---  | ---
**Purchase event tracking**                       |      | ✔️
**All dynamic remarketing events**                |      | ✔️
**Purchase transaction ID**                       | ✔️    | ✔️
**Purchase currency**                             | ✔️    | ✔️

### Pinterest Ads

Feature                                           | free | pro
---                                               | ---  | ---
**Purchase event tracking**                       |      | ✔️
**All dynamic remarketing events**                |      | ✔️
**Purchase transaction ID**                       | ✔️    | ✔️
**Purchase currency**                             | ✔️    | ✔️


## Plugin Compatibility List

For one or another reason we've tested the plugin together with third party plugins. The following list shows which third party plugins we've tested and how well our plugins works along with them. This is not an exhaustive list and we'll add more case by case.  

If a third plugin is marked with full compatibility, you shouldn't expect any issues. Plugins that we've marked with partial compatibility have proven to break the output of our plugin under certain conditions and lead to unexpected behavior.

### General Plugins

Plugin                          | full | partial
---                             | ---  | ---
**WPML**                        | ✔️    |
**Yoast SEO**                   | ✔️    |
**Google Site Kit**             |      | ✔️

* We have seen  that using Google Site Kit alongside with our plugin can cause purchases not to be tracked in Google Analytics. We're not sure yet if this happens on all installs or just when certain settings in Google Site Kit are enabled. 


### WooCommerce Extensions

Plugin                              | full | partial
---                                 | ---  | ---
**WooCommerce Brands**              | ✔️    |
**WooCommerce Wishlists**           | ✔️    |
**WooCommerce Google Product Feed** | ✔️    |
**YITH WooCommerce Brands**         | ✔️    |
**YITH WooCommerce Wishlist**       | ✔️    |
**Woo Discount Rules**              | ✔️    |
**WP Marketing Robot Feed Manager** | ✔️    |


### JavaScript Optimization Plugins

Plugin                          | full | partial | not yet tested
---                             | ---  | ---     | ---
**Autoptimize**                 | ✔️    |         | 
**WP Rocket**                   | ✔️    |         |
**W3 Total Cache**              | ✔️    |         | 
**LiteSpeed Cache**             | ✔️    |         | 
**SG Optimizer**                | ✔️    |         | 
**Swift Performance**           |      |         | ✔️
**WP Fastest Cache**            |      |         | ✔️
**Powerpack**                   |      |         | ✔️
**Breeze**                      |      |         | ✔️
**PhastPress**                  |      |         | ✔️
**WP Super Cache**              |      |         | ✔️
**PageSpeed Ninja**             |      |         | ✔️
**Comet Cache**                 |      |         | ✔️
**Hummingbird**                 |      |         | ✔️

?> If a plugin that you are using has not been tested yet, please put in a feature request which will allow us to prioritize it. Feature requests can be posted on our [roadmap](https://app.productstash.io/roadmaps/603366a462b3c30029854c2f/public).


### Cookie Consent Plugins

Plugin                                          | full | partial
---                                             | ---  | ---
**Borlabs Cookie**                              | ✔️    |
**GDPR Cookie Consent**                         | ✔️    |
**Cookie Notice & Compliance for GDPR / CCPA**  | ✔️    |
**Cookiebot**                                   | ✔️    |


\* Only if the "Maximum Compatibility Mode" is enabled in the plugin.

## Support

Service                                        | free | pro
---                                            | ---  | ---
**Fixing issues caused by our plugin**         | ✔️    | ✔️
**Support within 5 business days**             | ✔️    | ✔️
**Support within 24h (during business days)**  |      | ✔️


## Roadmap

[Roadmap](https://app.productstash.io/roadmaps/603366a462b3c30029854c2f/public ':include :type=iframe width=100% height=400px')