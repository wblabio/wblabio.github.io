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

!> This method doesn't work well with HTML caching enabled. Disable HTML caching if you want to used this method. We are working on a new method that will be HTML cache friendly. 

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
function adjust_analytics_parameters($analytics_id, $analytics_parameters){
    
    unset($analytics_parameters['anonymize_ip']);
    return $analytics_parameters;
}
```

The following code will adjust the parameters only for the given Google Analytics property:

```php
add_filter('woopt_pm_analytics_parameters', 'adjust_analytics_parameters', 10,2);
function adjust_analytics_parameters($analytics_id, $analytics_parameters){

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
function adjust_analytics_parameters($analytics_id, $analytics_parameters){

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