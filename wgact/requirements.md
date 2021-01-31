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

That is generally the case for onsite payment gateways. 

Offsite payment gateways need to be configured properly in order to redirect to the purchase confirmation page. 

?> We don't recommend offsite payment gateways out of two reasons:

1. They need to be configured properly in order for the conversion tracking to work  (redirect to the purchase confirmation page).
2. Buyers may stop the redirect to the purchase confirmation page during the checkout. In that case the purchase confirmation will not be tracked. 

## Caching 

!> Turn off caching for all cart and checkout pages.

You will need to make sure that the cart and checkout pages are excluded from caching. Otherwise conversion tracking won't work. 

## Minification

!> We have found that some caching and minification plugins alter the conversion code and break the conversion tracking. Make sure to disable those first when you run into troubles. 
