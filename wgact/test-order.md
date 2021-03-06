### Test order

> In order to find out if the conversion tracking works, the best way is to test it by placing an order and wait until conversion is reported. Please follow the instructions **exactly**. All steps are important in order to ensure a valid test. 

1. Turn off any kind of caching and / or minification plugins (because the can break the tracking code) 
2. Disable order deduplication in the advanced menu of the plugin (remember to re-enable deduplication once done with testing)
2. Log out of the shop (because admins and shop managers are excluded from tracking)
3. Turn off any kind of ad or script blocker in your browser (because they can disable the tracking code)
4. Search for one of your keywords and click on one of your ads
5. Purchase an item from your shop
6. Wait up to 48 hours until the conversion shows up in Google Ads. (usually takes only a few hours). When you look at the report in Google ads make sure the date range includes the dates of the ad click and the current date. 

?> The plugin by default deduplicates orders on the order confirmation page. This logic can be turned off in the plugin settings for temporary testing. Sometimes it is more convenient to keep the setting enabled and use the URL parameter `nodedupe` on the purchase confirmation page. When added to the purchase confirmation URL, all deduplication logic will be turned off. Example: Take the order confirmation URL `https://example.test/checkout/order-received/123/?key=wc_order_123abc` add a `&` and then add `nodedupe`. You should end up with this URL: `https://example.test/checkout/order-received/123/?key=wc_order_123abc&nodedupe`