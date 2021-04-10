### Order deduplication

> The order deduplication logic uses several methods to prevent orders to be double counted. Without that logic Google Analytics, Facebook and other pixels often would count the same order twice. 

Order duplication is more common than expected. In average revenue reports can become inflated by 10% to 20%, sometimes even much more. This is not within tolerable limits. Therefore we implemented a few smart methods to prevent purchase conversion pixels to be fired more than once. 

?> Basic order deduplication uses cookies and the browser storage to detect if a browser tries to send the same conversion more than once. When a conversion is fired, that conversion is saved within the same browser. If the visitor reloads the page, or revisits the page after a while, the pixel manager prevents the conversion pixels to be fired again. This method alone brings the inflated revenue down to 2% - 4%. 

Much better, right? We can do even more!

?> Advanced order deduplication (which is available for pro users only, available [here](https://woopt.com/pricing/)) adds one more layer of deduplication. Once the browser based deduplication has run, we also store that event in the WooCommerce oder database. No matter on which device the purchase confirmation is re-opened, this method will prevent the conversion to be fired ever again.  

### Ignore failed orders

The pixel manager detects orders with failed payments and doesn't fire the conversion pixels in order to increase measurement accuracy. 

### Ignore orders from admins and shop managers

When admins and shop managers place orders, in almost every case, this happens because they want to test orders. Usually we don't want to count test orders as a conversion. If you are sure you want a conversion for a test order to be counted, please follow the [test order procedure](test-order.md) and turn off order deduplication in the plugin settings. 