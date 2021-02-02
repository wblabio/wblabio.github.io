# Developers

> One of our goals is to make the plugin developer friendly by providing functionality like filters. The filters help adjust the behavior of the plugin programmatically. This can be interesting for other plugin developers who want to interact with our plugin, or for developers who want to tweak the output of the plugin. 

### Conversion Value Filter

> Use the conversion value filter in order to recalculate the conversion value. The output will only affect the conversion value of the paid ads pixels. The Google Analytics conversion value output will not be touched. 

`add_filter( 'wgact_conversion_value_filter', array( $this, 'filter_conversion_value' ), 10, 2 );`


Example:

```php
add_filter( 'wgact_conversion_value_filter', array( $this, 'filter_conversion_value' ), 10, 2 );

public function filter_conversion_value( $order_total, $order ) {

    // The order total is the value that is being output as configured within the plugin
    // If you wish to override this and calculate the value from scratch, 
    // the filter also provides the order object with the raw order values.

    // Example: The average cost to prepare an order for shipping is 10% of the order value.
    // Therefore we remove 10% of the order value on each order.

    return $order_total * 0.9;
}
```


### Disable Pixel Output

> In some cases, developers want to disable the pixel injection into the website. That could be the case for consent management platforms that only want to allow pixel injection in case the visitor has given explicit consent. 

`add_filter( 'wgact_cookie_prevention', '__return_true' );`