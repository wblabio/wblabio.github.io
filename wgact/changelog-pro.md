== Changelog ==

= 1.9.4 =

* New: add_to_wishlist event for GA and Facebook
* New: InitiateCheckout event for FB
* New: Send purchase events using the GA UA Measurement Protocol
* New: Send subscription renewal purchase events using the GA UA Measurement Protocol
* New: Send full refund events using the GA UA Measurement Protocol
* New: Send partial refund events using the GA UA Measurement Protocol
* New: Send purchase events using the GA 4 Measurement Protocol
* New: Send subscription renewal purchase events using the GA 4 Measurement Protocol
* New: Send full refund events using the GA 4 Measurement Protocol
* New: Send partial refund events using the GA 4 Measurement Protocol
* Tweak: Only activate eec scripts if GA UA or GA4 are enabled
* Tweak: Finalized improvement for front-end error handling
* Tweak: Added a JS modification exclusion for Autoptimize in order to prevent our script to get modified and broken
* Fix: Fixed a selector for cart items on the cart page which caused on certain custom shop templates to trigger an error

= 1.9.3 =

* Tweak: Added one more layer of safeguards if wooptpm.js can't evaluate the current productId

= 1.9.2 =

* Tweak: Added one more safeguard if wooptpm.js can't evaluate the current productId

= 1.9.1 =

* Tweak: Much better selector for view_item_list trigger
* Tweak: Added some some safeguards in order to stop processing in case no productId can be evaluated
* Tweak: Removed deprecated "disable gtag insertion" feature entirely


= 1.9.0 =

* New: Implemented view_item event for variations when selected on the product page
* New: Implemented view_search_results event
* Tweak: Use proper select_item event in GA4 not the deprecated select_content event anymore
* Tweak: Moved view_item event processing entirely to front-end
* Tweak: Improved selector for products if WPML WC multi currency is being used
* Tweak: Better test to check if WPML WC multi currency is active
* Tweak: Improved function to get the productId on select_item event
* Tweak: Additional caching exclusions for SG Optimizer
* Tweak: Changed the gtag code in order to make it better testable
* Tweak: Moved some scripts to the footer
* Tweak: Improved add_to_cart trigger
* Tweak: Refactored view_item_list event entirely to be unaffected by caching mechanisms
* Tweak: Added a new view_item_list trigger with some interesting options
* Fix: Fixed front-end triggers for Google and Facebook to only fire if the pixels are enabled
* Fix: Fixed an array check if an old WP Rocket version was installed and threw a notice about a missing array index
* Fix: Output correct price if WPML Multilingual with Multi-currency is running

= 1.8.28 =

* New: Filter to switch Google Analytics ID output to SKU
* New: Process discounted order item price for GA if Woo Discount Rules is active
* New: Implemented all main GA4 events
* New: Logged in event for GA
* New: Google user ID tracking
* Tweak: Twitter ID check now allows numbers too
* Tweak: Moved getCartItemsFromBackEnd to document.load event
* Tweak: Added Freemius purchase conversion
* Tweak: Avoid number output with too many decimals
* Tweak: More reliable method to get order from order received page
* Fix: Imported necessary classes for refunds
* Fix: Proper variable types for purchase confirmation variables
* Fix: Initialize wooptpmDataLayer.pixels early, so that all pixels can use it
* Fix: Replaced $order->get_id() with $order->get_order_number in order to fix a bug on a small subset of shops
* Fix: Get proper WP db prefix for refunds SQL query

= 1.8.27 =

* Tweak: LD check

= 1.8.26 =

* Tweak: Implemented permanent compatibility mode for SG Optimizer
* Tweak: Implemented permanent compatibility mode for LiteSpeed Cache
* Tweak: Refactored the Facebook pixel and events

= 1.8.25 =

* Tweak: Implemented permanent compatibility mode for WP Rocket
* Fix: Refactored a JavaScript regex that was not working in Safari

= 1.8.24 =

* Fix: Added a function that should be available in the free version conversion_pixels_already_fired_html

= 1.8.23 =

* Fix: Include output of variable products into the visible_products object
* Fix: Added a missing opening tag for shops that are still using the gtag deactivation option

= 1.8.22 =

* New: Added Google Analytics eec begin_checkout event
* New: Added Google Analytics eec set_checkout_option events
* New: Added Google Analytics eec refund events
* New: Added initial GA 4 eec events (needs more tweaking though)
* Tweak: Added Google Analytics eec add_to_cart event for all /?add-to-cart=123 link clicks
* Tweak: Partially decoupled pixels from pixel manager
* Tweak: Refactored browser e-commerce events into pubsub
* Fix: Added proper phone conversion label
* Fix: Under some circumstances rating_done is not set in the wgact_ratings option. This fix adds this default option.
* Fix: Fixed the GA 4 config command

= 1.8.21 =

* New: Added Google Analytics eec product click events
* New: Added Google Analytics eec product add_to_cart and remove_from_cart events
* New: Added output of related up- and cross-sell product view_item_list list events for Google Ads dynamic remarketing
* New: Added &nodedupe URL parameter for testing the order confirmation page
* Tweak: Build in a fallback for misconfigured variable products that trigger an "Error: Call to a member function get_sku() on bool"

= 1.8.20 =

* Fix: Fixed the Google Analytics config filter

= 1.8.19 =

* New: Added Pro feature demo mode
* New: Added shortcodes for tracking leads and similar conversions
* New: Filter to adjust Google Analytics config parameters

= 1.8.18 =

* New: Added Borlabs support for Google Consent Mode
* New: Google Analytics link attribution
* Tweak: Bumping up WP supported version to 5.7
* Tweak: Some code syntax cleanup
* Fix: Fixed the country name for Macedonia in Google consent mode
* Fix: Fixed duplicated jobs option in Google business verticals

= 1.8.17 =

* Tweak: Remove some freemius options

= 1.8.16 =

* New: Google Analytics enhanced e-commerce
* New: Added Google consent regions setting
* New: Output the variation ID for dynamic remarketing
* New: Maximum compatibility mode
* Tweak: Strip HTML tags from description in microdata output for Facebook
* Tweak: Added item_group_id to microdata output for Facebook
* Tweak: Switched logic to activate conversion cart data automatically when merchant center ID is set
* Tweak: Made Google Analytics always receive the post ID as product ID because this is more robust
* Tweak: Removed some unnecessary text output in the settings
* Fix: Script blocker documentation link

= 1.8.15 =

* New: Added Facebook microdata output
* Fix: Determine correctly new customer for shopping cart data on new customers who paid immediately
* Tweak: Created new trait to calculate brand for product
* Tweak: Added a new array with additional product attributes (like brand which is calculated)
* Tweak: added ability to load traits in autoload.php
* Tweak: Bumped up WC version
* Tweak: Added an additional is_array() check in order to suppress a PHP 7.4 notice when checking the environment

= 1.8.14 =

* Tweak: Make the <noptimize> tag only appear if Autoptimize is active
* Tweak: Removed a duplicate filter
* Fix: Moved get_cart() query into is_cart() condition

= 1.8.13 =

* New: Filter to prevent conversion pixels to fire on purchase confirmation page
* Tweak: Replaced _e() with echo where necessary
* Tweak: Syntax cleanup

= 1.8.12 =

* Tweak: Calculate filtered order total for all pixels

= 1.8.11 =

* Tweak: Added product IDs to Microsoft Advertising purchase event
* Fix: Removed a function call where the function was missing

= 1.8.10 =

* New: Google consent mode
* New: Setting for cookiebot
* New: Added advanced order deduper
* Tweak: Removed Pinterest noscript tags
* Fix: Added product IDs to Microsoft Advertising purchase event
* New: Added basic order deduper
* New: Google Shopping new_customer parameter
* New: Added switch to enable transaction deduping (default enabled)
* Tweak: Product identifier output now for all the same
* Tweak: Adjusted the HTML comment output
* Tweak: Added new cookie for Borlabs Cookie
* Tweak: Made some input elements clickable
* Tweak: Moved check for failed payments and admin and shop manager up to the pixel manager

= 1.8.9 =

* Tweak: readme.txt links
* Tweak: fallback to post ID in case the SKU is not set
* Tweak: Adjusted the HTML comments
* Tweak: Don't inject cart scripts on cart page if cart is empty

= 1.8.8 =

* Tweak: Adjusted directory name
* Tweak: Bumped up version
* Tweak: Changed regex for GMC IDs to allow 7 digit IDs
* Tweak: Improved speed to hide script blocker warning
* Tweak: Adjusted documentation links

= 1.8.7 =

* Fix: Added new classes to SVN

= 1.8.6 =

* Tweak: Code cleanup
* Tweak: Adjusted doc links

= 1.8.5 =

* Tweak: Bing dynamic remarketing events
* New: Hotjar pixel

= 1.8.4 =

* New: Microsoft Ads pixel
* New: Twitter pixel
* New: Pinterest pixel
* New: Hotjar pixel
* Tweak: Renamed subsection 'Order Logic' to 'Shop'
* Tweak: Refactored debug info
* Tweak: Added WP Rocket JavaScript concatenation to debug info

= 1.8.3 =

* New: Google business vertical setting

= 1.8.2 =

* New: Check for WP Rocket JavaScript concatenation
* New: Added filter which helps adding multiple additional conversion IDs and labels

= 1.8.1 =

* Fix: Version number
* Fix: FB default pixel id

= 1.8.0 =

* New: Google Analytics UA standard beta
* New: Google Analytics 4 beta
* New: Google Optimize beta
* New: Activation indicators
* Tweak: Put admin scripts into header for faster rendering
* Fix: Detect proper admin path in tabs.js

= 1.7.13 =

* New: Facebook pixel
* Tweak: Adjust db and bump up to version 3
* Tweak: Introduced Pixel_Manager and restructured Google Ads class

= 1.7.12 =

* Fix: Removed namespace for main class because it was conflicting with freemius in some cases

= 1.7.11 =

* Fix: Directory name fix
* New: Warning message if an ad- or script-blocker is active
* Tweak: Improved one of the db saving functions
* Tweak: Start using namespaces


= 1.7.10 =

* Fix: child theme detection

= 1.7.9 =

* Fix: Roll back to 1.7.7 since namespace don't work everywhere
* Fix: child theme detection

= 1.7.8 =

* New: Warning message if an ad- or script-blocker is active
* Tweak: Improved one of the db saving functions
* Tweak: Start using namespaces

= 1.7.7 =

* Fix: Don't show the rating popup if an admin uses a script blocker

= 1.7.6 =

* Fix: Improved check if dynamic remarketing settings already has been set before checking for it.
* Fix: Saving to the database threw sometimes warnings that have been fixed.
* Tweak: Styling changes

= 1.7.5 =

* New: Added checks for freemius servers
* New: Dynamic remarketing pixels
* New: Deactivation trigger for the WGDR plugin if dynamic remarketing is enabled
* Fix: Adjusted the cookie name for Cookie Law Info
* Fix: Improved detection if WooCommerce is active on multisite
* Fix: Fixed default setting for conversion_id
* Tweak: Added back rating testing code
* Tweak: Adjusted some links
* Tweak: Code style cleanups

= 1.7.4 =

* Fix: Fixed the ask for rating constant

= 1.7.3 =

* Fix: Don't open the rating page if user clicks on already done
* Tweak: Backward compatibility to PHP 7.0

= 1.7.2 =

* Fix: Fixed a printf syntax error that caused issues on some installations

= 1.7.1 =

* Tweak: Removed deletion of settings on uninstall in order to preserve the settings

= 1.7.0 =

* New: Added German translations
* Fix: Reversed some code in freemius to make it compatible with older versions of PHP (< PHP 7.2)
* Fix: Fixed the uninstall hook for it to work with freemius
* Tweak: Added some comments for translators
* Tweak: Removed old language packs
* Tweak: Add gtag config if gtag insertion is disabled
* Tweak: Rating request improved
* Tweak: Removed plugin ads
* Tweak: Added documentation
* Tweak: Updated db scheme
* Tweak: Merge new default options recursively
* Tweak: On save merge new and old options recursively, set missing checkbox options to zero, omit db_version

= 1.6.17 =

* Tweak: Reactivate freemius

= 1.6.16 =

* Fix: Deactivate freemius

= 1.6.15 =

* Tweak: Adjusted freemius main slug for plugin

= 1.6.14 =

* New: Implemented Freemius telemetry
* Tweak: Adjustments to the descriptions and links to new documentation
* Tweak: Only run if WooCommerce is active

= 1.6.13 =

* New: Implemented framework for sections and subsections
* Tweak: Some code cleanup
* Tweak: Made strings more translation friendly
* Tweak: Properly escaped all translatable strings
* Fix: Textdomain

= 1.6.12 =

* New: Plugin version output into debug info
* Fix: Conversion id validation
* Tweak: Moved JavaScript to proper enqueued scripts
* Tweak: Bumped up WC and WP versions

= 1.6.11 =

* New: Tabbed settings
* New: Debug information
* Tweak: Code style adjustments

= 1.6.10 =

* Fix: Disabled some error_log invocation since it can cause issues in some rare server configurations

= 1.6.9 =

* Fix: Re-enabled settings link on plugins page

= 1.6.8 =

* Fix: Changed how Borlabs Cookie activation works

= 1.6.7 =

* Fix: Implemented check for Borlabs minimum version

= 1.6.6 =

* New: Added option to disable the pixel with a filter add_filter( 'wgact_cookie_prevention', '__return_true' )
* New: Added Borlabs cookie management approval for marketing
* Tweak: Refactored the code into classes

= 1.6.5 =

* Tweak: Removed duplicate noptimize tag
* Tweak: Removed CDATA fix since it is not necessary anymore with the new conversion tag

= 1.6.4 =

* Fix: Fixed the calculation for the non-default order total value (which includes tax and shipping)

= 1.6.3 =

* Info: Tested up to WP 5.4

= 1.6.2 =

* Tweak: More reliable method to detect the visitor country added

= 1.6.1 =

* New: Add Cart Data feature
* New: Added a switch to disable the insertion of the gtag
* Tweak: Added more descriptions on the settings page
* Tweak: Code optimisations

= 1.5.5 =

* Tweak: Made the conversion ID and label validation code more robust

= 1.5.4 =

* Tweak: Updated function that inserts the settings link on the plugins overview page

= 1.5.3 =

* Info: Tested up to WP 5.2

= 1.5.2 =

* Fix: Correctly calculate the value when no filter is active

= 1.5.1 =

* Tweak: Re-enabled order value filter

= 1.4.17 =

* Info: Tested up to WP 5.1

= 1.4.16 =

* Info: Updated a few text strings

= 1.4.15 =

* Info: Changing name from AdWords to Google Ads

= 1.4.14 =

* Info: Tested up to WC 3.5.3

= 1.4.13 =

* Info: Tested up to WC 3.5.2

= 1.4.12 =

* Tweak: bumping up the WC version

= 1.4.11 =

* Tweak: remove some debug code
* fix: properly save the order_total_logic option

= 1.4.10 =

* Tweak: switched sanitization function to wp_strip_all_tags

= 1.4.9 =

* Tweak: Added input validation and sanitization
* Tweak: Added output escaping

= 1.4.8 =

* Tweak: Added discounts into order value calculation

= 1.4.7 =

* New: Switched over to the newest version of the AdWords conversion tracking pixel

= 1.4.6 =

* Tweak: Disabled minification through Autoptimize

= 1.4.5 =

* Tweak: Order ID back in apostrophes

= 1.4.4 =

* Tweak: Switched on JavaScript tracking with a fix for the CDATA bug http://core.trac.wordpress.org/ticket/3670
* Tweak: The correct function is being used to get the currency depending on the WooCommerce version
* Fix: Added missing </noscript> tag

= 1.4.3 =

* Tweak: Remove campaign URL parameter

= 1.4.2 =

* Fix: Backward compatibility for $order->get_currency()

= 1.4.1 =

* Tweak: Making the plugin PHP 5.4 backwards compatible
* Fix: Fixing double counting check logic

= 1.4 =

* New: Ask kindly for a rating of the plugin
* New: Add a radio button to use different styles of order total
* Tweak: Consolidate options into one array
* Tweak: Code cleanup

= 1.3.6 =

* New: WordPress 4.8 compatibility update
* Tweak: Minor text tweak.

= 1.3.5 =

* Fix: Fixed a syntax error that caused issues on some installations.

= 1.3.4 =

* Tweak: Added some text output to make debugging for users easier.

= 1.3.3 =

* Tweak: Refurbishment of the settings page

= 1.3.2 =

* New: Uninstall routine

= 1.3.1 =

* New: Keep old deduplication logic in the code as per recommendation by AdWords

= 1.3.0 =

* New: AdWords native order ID deduplication variable

= 1.2.2 =

* New: Filter for the conversion value

= 1.2.1 =

* Fix: wrong conversion value fix

= 1.2 =

* New: Filter for the conversion value

= 1.1 =

* Tweak: Code cleanup
* Tweak: To avoid over reporting only insert the retargeting code for visitors, not shop managers and admins

= 1.0.6 =

* Tweak: Switching single pixel function from transient to post meta

= 1.0.5 =

* Fix: Adding session handling to avoid duplications

= 1.0.4 =

* Fix: Skipping a tag version

= 1.0.3 =

* Fix: Implement different logic to exclude failed orders as the old one is too restrictive

= 1.0.2 =

* Fix: Exclude orders where the payment has failed

= 1.0.1 =

* New: Banner and icon
* Update: Name change

= 1.0 =

* Update: Release of version 1.0!

= 0.2.4 =

* Update: Minor update to the internationalization

= 0.2.3 =

* Update: Minor update to the internationalization

= 0.2.2 =

* New: The plugin is now translation ready

= 0.2.1 =

* Update: Improving plugin security
* Update: Moved the settings to the submenu of WooCommerce

= 0.2.0 =

* Update: Further improving cross browser compatibility

= 0.1.9 =

* Update: Implemented a much better workaround tor the CDATA issue
* Update: Implemented the new currency field
* Fix: Corrected the missing slash dot after the order value

= 0.1.8 =

* Fix: Corrected the plugin source to prevent an error during activation

= 0.1.7 =

* Significantly improved the database access to evaluate the order value.

= 0.1.6 =

* Added some PHP code to the tracking tag as recommended by Google.

= 0.1.5 =

* Added settings field to the plugin page.
* Visual improvements to the options page.

= 0.1.4 =

* Changed the woo_foot hook to wp_footer to avoid problems with some themes. This should be more compatible with most themes as long as they use the wp_footer hook.

= 0.1.3 =

* Changed conversion language to 'en'.

= 0.1.2 =

* Disabled the check if WooCommerce is running. The check doesn't work properly with multisite WP installations, though the plugin does work with the multisite feature turned on.
* Added more description in the code to explain why I've build a workaround to not place the tracking code into the thankyou template of WC.

= 0.1.1 =

* Some minor changes to the code

= 0.1 =

* This is the initial release of the plugin. There are no known bugs so far.
