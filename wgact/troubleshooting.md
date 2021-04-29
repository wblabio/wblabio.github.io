### Where can I report a bug or suggest improvements?

Please post your problem in the WordPress support forum for this plugin: [Support forum](https://wordpress.org/support/plugin/woocommerce-google-adwords-conversion-tracking-tag)

Alternatively you can sent a request to [support@wolfundbaer.ch](mailto:support@wolfundbaer.ch). If you do, please copy and paste the debug info from our plugin and attach it to the email. 

<details>
<summary>image (Click to expand)</summary>

![Copy the debug info](_media/copy-debug-info.png)
</details>

### The most common issues in case the pixels don't work

- Caching: If you run some caching layer, the server might still serve cached versions of the pages. You will need to delete the cache.
- Minification, combination and concatenation: Some minification and combination plugins mangle up the injected JavaScript code to an extend, that the tracking pixels stop working. You will need to turn minification, combination and concatenation off and try again. 


### WP Rocket JavaScript concatenation

We received numerous reports where the WP Rocket JavaScript concatenation function has broken the pixel output of our plugin. In the attempt to optimize JavaScripts, WP Rocket changes the code to an extent that the tracking pixels won't work anymore. 
 
We tried several exclusion settings in WP Rocket's JavaScript concatenation setting fields, but none of them worked. 
 
?> If you want the WooCommerce Pixel Manager plugin to work properly, you will have to disable the WP Rocket JavaScript concatenation.

### LiteSpeed Cache Inline JavaScript After DOM Ready

We received numerous reports where the LiteSpeed Cache Inline JavaScript After DOM Ready function has broken the pixel output of our plugin. In the attempt to optimize JavaScripts, LiteSpeed Cache changes the code to an extent that the tracking pixels won't work anymore. 

?> If you want the WooCommerce Pixel Manager plugin to work properly, you will have to disable LiteSpeed Cache Inline JavaScript After DOM Ready.

### Is wooptpm_get_cart_items slowing down my website?

Short answer: **No**

Long answer: 

First some information on what `wooptpm_get_cart_items` is doing. 

> While a visitor is browsing a shop he might add some products to the cart. Each time he uses the minicart to modify his selection, by adding or removing products, we need to make sure to have all product information handy in order to send pixel events with all relevant data to Google, Facebook, etc. Unfortunately it is not possible to include this information on page load within the HTML code, because caching mechanisms could serve outdated data to the browser. That's why we need a mechanism like `wooptpm_get_cart_items` that will fetch all the current product data for the minicart from the server. 

And now to the question *if* `wooptpm_get_cart_items` is slowing down the website. 

Some users have noticed in the network tab of their browsers that the `wooptpm_get_cart_items` call adds one more request, which on slow servers can take even more than a second to fullfil. It is using the standard WordPress Ajax function to fetch the product data. 

But, why am I saying that this is **not** slowing down the website? 

The `wooptpm_get_cart_items` call happens **after** the browser has signalled the load event, *which happens when all content has already been successfully loaded*.

?> The load event is fired when the whole page has loaded, including all dependent resources such as stylesheets and images.

Reference: [Mozilla MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Window/load_event)

?> PageSpeed measures the loading time of your page starting from the initial request to when the last embedded resource (JS, CSS, images, etc.) has finished loading. So that’s essentially when $(window).load() is triggered.

Reference: [Lèse Majesté's answer on Stackoverflow](https://webmasters.stackexchange.com/a/39512/51846)

So the `wooptpm_get_cart_items` doesn’t slow down the download or rendering of a WooCommerce shop in any way.


