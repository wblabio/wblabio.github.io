# Filters

> While our goal is to make the plugin very simple to use through the user interface, this can be limiting for users and developers who need much more granular control over the plugin's output. For those users we provide filters which give them the option to adjust the plugin's behavior programmatically, making the options almost limitless.

> If you think there is a good use case for a new filter, let us know by sending a feature request [here](https://app.productstash.io/woopt-woocommerce-pixel-manager). 


## Conversion Value Filter

> Use the conversion value filter in order to recalculate the conversion value. The output will only affect the conversion value of the paid ads pixels. The Google Analytics conversion value output will not be touched. 

`add_filter( 'wgact_conversion_value_filter', array( $this, 'filter_conversion_value' ), 10, 2 );`


Example:

```php
add_filter( 'wgact_conversion_value_filter', array( $this, 'filter_conversion_value' ), 10, 2 );

public function filter_conversion_value( $order_total, $order ) {

    /** 
    * The order total is the value that is being output as configured 
    * within the plugin. If you wish to override this and calculate 
    * the value from scratch, the filter also provides the order object 
    * with the raw order values.
    *
    * Example: The average cost to prepare an order for shipping is 
    * 10% of the order value. Therefore we remove 10% of the order value on 
    * each order.
    **/

    return $order_total * 0.9;
}
```


## Disable Pixel Output

> In some cases, developers want to disable the pixel injection into the website. That could be the case for consent management platforms that only want to allow pixel injection in case the visitor has given explicit consent. 

!> This method doesn't work well with HTML caching enabled. Disable HTML caching if you want to use this method. We are working on a new method that will be HTML cache friendly. 

`add_filter( 'wgact_cookie_prevention', '__return_true' );`


## Additional Google Ads Conversion Pixels

> With the following filter we provide a way ot add more than one Google Ads conversion pixel programmatically.


[Add conversion identifiers to the Google Ads pixel output](https://gist.githubusercontent.com/alewolf/d49a788da470de69dc9c6bc60fbef352/raw/wgact_google_ads_conversion_identifiers.php ':include :type=code')


## Adjust Google Analytics Config Parameters

> To keep the user interface lightweight we only included basic parameters like Enhanced Link Attribution. For those who need much more granular control over the Google Analytics config parameters we provide a filter. The filter can also be used to override parameters from the user interface.

?> When setting a parameter to `true`or `false` make sure to wrap the setting into single quotes ('true' or 'false') in order to make sure that it'll be output as text and not as boolean. 

The following code will remove the `anonymize_ip` parameter on all Google Analytics configs:

```php
add_filter('woopt_pm_analytics_parameters', 'adjust_analytics_parameters', 10,2);
function adjust_analytics_parameters($analytics_parameters, $analytics_id){
    
    unset($analytics_parameters['anonymize_ip']);
    return $analytics_parameters;
}
```

The following code will adjust the parameters only for the given Google Analytics property:

```php
add_filter('woopt_pm_analytics_parameters', 'adjust_analytics_parameters', 10,2);
function adjust_analytics_parameters($analytics_parameters, $analytics_id){

  if('UA-12345678-3' == $analytics_id){

    unset($analytics_parameters['anonymize_ip']);

    /** 
    * Wrap `true` into single quotes ('true') in order to make sure 
    * that it is output as text and not as boolean.
    *
    * The following parameter setting will override the one set 
    * in the user interface.
    **/
    $analytics_parameters['link_attribution'] = 'true'; 
  }

  return $analytics_parameters;
}
```

Or maybe, you want to set much more specific settings for `link_attribution` like specified [here](https://developers.google.com/analytics/devguides/collection/gtagjs/enhanced-link-attribution#customizing_enhanced_link_attribution):

```php
add_filter('woopt_pm_analytics_parameters', 'adjust_analytics_parameters', 10,2);
function adjust_analytics_parameters($analytics_parameters, $analytics_id){

  if('UA-12345678-3' == $analytics_id){

    $analytics_parameters['link_attribution'] = [
      'cookie_name' => '_gaela',
      'cookie_expires' => 60,
      'levels' => 2
    ]; 
  }

  return $analytics_parameters;
}
```

## Product ID Output Filter for Paid Ads Pixels

> To keep the UX simple and the setup consistent over several advertising channels, there is only one setting in the UX to adjust the product ID output. The same ID then will be used for all paid ads pixels. The standard setting is either the post ID (eg. `14`), the ID for the WooCommerce Google Feed plugin (eg. `woocommerce_gpf_14`) or the SKU (eg. `Hoodie`). In some cases you might need to use a different ID type on different channels. Maybe you're using the post ID for Google Ads, and the SKU for Facebook. In this case the following filter will adjust the output for a specific pixel. It is even possible to completely customize the ID, if necessary. 

?> We strongly recommend to use the post ID for all product catalogs and for the product ID output. It is the most compatible way and causes the least troubles. 

> By adding the pixel name to the filter name, you can chose which pixel you want to adjust. For Facebook use `wooptpm_product_id_type_for_facebook`, for Microsoft Ads (Bing) use `wooptpm_product_id_type_for_bing`, etc. Depending on which version of the plugin you have, you can use the following pixel filters: `google_ads`, `facebook`, `bing`, `twitter`, `pinterest`

> The default values are `post_id` for the post ID, `gpf` for the WooCommerce Google Feed ID output (eg. `woocommerce_gpf_14`) and `sku` for the SKU. 

Here's an example on how to switch the product ID output for Facebook to the `SKU`:

```php
add_filter('wooptpm_product_id_type_for_facebook', 'product_id_type_output_for_facebook');
function product_id_type_output_for_facebook()
{
  return 'sku';
}
```


Here's an example to switch the Facebook output to post ID:

```php
add_filter('wooptpm_product_id_type_for_facebook', 'product_id_type_output_for_facebook');
function product_id_type_output_for_facebook()
{
  return 'post_id';
}
```

> You have even the option to completely customize the product ID output and assign it to a specific channel with the `wooptpm_product_ids` filter.

In the following example use the `wooptpm_product_ids` filter to add one or more custom IDs for each product. 
In a second step, use the `wooptpm_product_id_type_for_` filter to assign the new custom ID to one or more specific pixels. 

```php
add_filter('wooptpm_product_ids', 'return_wooptpm_dyn_r_product_ids', 10, 2);
function return_wooptpm_dyn_r_product_ids($product_ids, $product)
{
  $product_ids['custom1'] = 'custom_type_' . $product->get_id();
  $product_ids['custom2'] = 'custom_pinterest_catalog_' . $product->get_sku();

  return $product_ids;
}
```

```php
add_filter('wooptpm_product_id_type_for_google_ads', 'product_id_type_output_for_google_ads');
function product_id_type_output_for_google_ads()
{
  return 'custom1';
}
```

```php
add_filter('wooptpm_product_id_type_for_pinterest', 'product_id_type_output_for_pinterest');
function product_id_type_output_for_pinterest()
{
  return 'custom2';
}
```

## Google Analytics Product ID Output Filter

> By default the plugin uses the `post ID` as identifier for Google Analytics. This filter allows you to change this to the `SKU`. 

?> The main reasons why the plugin uses the `post ID` by default are: 1) The `post ID` is more reliable. A shop owner might not add SKUs to all products, leaving the field empty. But we need to send an identifier to Google Analytics. (In the case the shop owner doesn't add a SKU to a product, we will fall back to the `post ID`.) 2) The products can be identified by the product name in Google Analytics anyway. 3) It is easier to search for a product ID in WooCommerce or in Google Analytics, so it's more practical to use the `post ID`.

```php
add_filter('wooptpm_product_id_type_for_google_analytics', 'wooptpm_product_id_type_for_google_analytics');
function wooptpm_product_id_type_for_google_analytics()
{
    return 'sku';
}
```