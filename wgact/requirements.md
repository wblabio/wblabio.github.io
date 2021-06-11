# Requirements

> In order for this plugin to work properly a few requirements need to be met. The plugin has been developed with maximum compatibility in mind. But, there are edge cases that we can't or that we don't want to cover. 

## Versions 

!> We only support the most current versions of WooCommerce, WordPress and PHP. 

There is some backward compatibility, but if things break you will need to  make sure that you're running the most current versions of WooCommerce, WordPress and PHP. 

We won't provide support for old versions of WooCommerce, WordPress or PHP. 

The minimum requirement for WordPress and WooCommerce are as follows:

[WordPress minimum requirements](https://wordpress.org/about/requirements/)

[WooCommerce minimum requirements](https://docs.woocommerce.com/document/server-requirements/)


## Payment gateways

> The plugin is 100% compatible with all payment gateways that redirect properly to the payment confirmation page after a purchase. 

That is generally the case for on-site payment gateways. 

Off-site payment gateways on the other hand cause problems.

!> We generally recommend to **avoid off-site payment gateways** because they impair the conversion tracking significantly. We've seen conversion tracking drops down to 20% of what should have been measured. Such low tracking accuracy as a consequence also impairs campaign optimization. 

But why do off-site payment gateways impair conversion tracking so much you might think. Here are the main reasons: 

1. The off-site payment gateway needs to be configured properly in order to redirect to the WooCommerce purchase confirmation page after a payment. If that redirect doesn't work in the first place, no conversions can be tracked at all. (The WooCommerce purchase confirmation page is where the conversion pixels are fired.)
2. Some off-site payment gateways would not automatically redirect back to the purchase confirmation page, but only after a click on a button by the buyer. Many buyers don't click that button. 
3. Buyers may even stop automatic redirects to the WooCommerce purchase confirmation page after they see that the purchase has been confirmed by the payment provider.

> What are off-site payment gateways? Off-site payment gateways redirect the visitor away from the shop domain to a domain belonging to the payment provider. They usually try to redirect the visitor back to the WooCommerce store once the payment has been made.

> What are on-site payment gateways? On-site payment gateways keep the visitor on the shop domain for checkout and usually automatically redirect to the WooCommerce purchase confirmation page once the payment has been confirmed. The purchase confirmation page is where the conversion pixels are fired. 

Here's a list of off-site payment gateways that you need to avoid:

- The PayPal standard payment gateway that comes pre-installed with WooCommerce
- All payment gateways on the following [list](https://woocommerce.com/product-category/woocommerce-extensions/payment-gateways/off-site-payment-gateways/?aff=48267). (Maybe some of the can be configured to be used on-site. In that case you can use them.)

If you are looking for a different on-site PayPal payment gateway have a look at this [list](https://docs.woocommerce.com/document/paypal-extension-comparison/?aff=48267).

Also WooCommerce has categorized all on-site payment gateways and listed them [here](https://woocommerce.com/product-category/woocommerce-extensions/payment-gateways/on-site/?aff=48267). Anyone of those should work well in theory. When you are setting up a new one make sure that it keeps the visitor on-site. 

## Caching 

!> Turn off caching for all cart and checkout pages.

You will need to make sure that the cart and checkout pages are excluded from caching. Otherwise conversion tracking won't work. 

## Minification

!> We have found that some caching and minification plugins alter the conversion code and break the conversion tracking. Make sure to disable those first when you run into troubles. 
