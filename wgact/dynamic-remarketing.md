# Dynamic Remarketing

### General Information

?>In order for the dynamic remarketing to work, you need to either upload your products into the platform catalog (Google Merchant Center for Google Ads, Facebook Catalog for Facebook, etc.) Google Merchant Center, or upload a custom business feed into your Google Ads account. 

?> We strongly recommend to upload the products with post ID as identifier. Using the SKU can lead to much more issues and more difficult situations to debug. 

1. Go the the beta section of the plugin and enable Dynamic Remarketing
2. Check your Product Identifier setting and adjust if necessary. **The product identifier must match the product identifiers that have been uploaded to the Google Merchant Center.**
3. The output for variations is enabled by default. This requires that you upload the product variations with your product feed as well, including the item_group_id. Depending on the feed plugin you use, this might be enabled or disabled by default. So make sure to double check. We recommend to include the variations into the upload. 

### Google Ads

There are several ways to upload your products to the Google Merchant Center. The easiest one is to use a feed plugin. So far, we can recommend the following two:

#### Google Merchant Center Feed

- [Google Product Feed by WooCommerce.com](https://woocommerce.com/products/google-product-feed/)
  - Relatively easy to use
  - Can't handle large feeds very well 
  - Only good for Google Ads and Microsoft Ads
- [WooCommerce Product Feed Manager by WPMarketingRobot](https://www.wpmarketingrobot.com/)
  - Many options, but comparably difficult to set up
  - Handles large feeds very well
  - Supports many marketing channels

#### Custom Business Feed

For countries where the Google Merchant Center is not available, you can upload your product using a custom business feed. [Create a feed](https://support.google.com/google-ads/answer/6077139)

You will also need to set the [Google Business Vertical](https://support.google.com/google-ads/answer/7305793#zippy=%2Ccustom) to 'custom'. This is available in the Pro version of our plugin.