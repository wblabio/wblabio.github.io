### Order deduplication

> The order deduplication logic uses several methods to prevent orders to be double counted. Without that logic Google Analytics, Facebook and other pixels often would count the same order twice. 

This is more common than expected. In average revenue reports can get inflated by 10% to 20%, in certain cases even much more. This is not within tolerable limits. Therefore the plugin comes with some smart methods to prevent purchase conversion cookies to be fired more than once. 

?> Basic order deduplication relies on cookie and browser storage based deduplication. When a conversion is fired, that conversion is saved within the same browser. If the visitor reloads the page, or revisits the page after a while, the pixel manager prevents the conversion pixels to be fired again.

?> Advanced order deduplication (pro version only) adds another layer of 

### Ignore failed orders

The pixel manager detects orders with failed payments and doesn't fire the conversion pixels in order to increase measurement accuracy. 

### Ignore orders from admins and shop managers

When admins and shop managers place orders, in almost every case this happens because they placed test orders. Usually we don't want to count test orders as a conversion. If you are sure you want a conversion for a test order to be counted, please follow the [test order procedure](test-order.md)