# General Settings

### Maximum Compatibility Mode

>This mode detects specific settings that cause issues with the front-end output of this plugin and protects the output from being altered. 

Over time and through many support requests we found certain third party plugins that cause issues with our plugin. One common example are caching and minification plugins that are adjusting the output of our plugin, in some cases break the scripts and stop the tracking pixels from working. 

Obviously this leads to hours of debugging, many support requests and as a consequence, unhappy users. 

Through thorough analysis we identified the exact settings in those third party plugins which cause those issues. The maximum compatibility mode changes those settings to values which make the third party plugins compatible with our plugin. We only do this with settings which are not essential to the working of the third party plugins. In cases where we would have to disable essential functionality of the third party plugins, we would no do this through the Maximum Compatibility Mode, but through displaying a warning notification in the back-end. The user would then have to decide himself how to proceed.

The Maximum Compatibility Mode alters following third party plugin settings:

- Disable WP Rocket JavaScript concatenation
- Disable LiteSpeed Cache Inline JavaScript Dom Ready adjustment
- Disable Yoast SEO Facebook Opengraph output in case the Facebook microdata output is enabled