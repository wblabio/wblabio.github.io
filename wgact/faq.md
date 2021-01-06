### What is the new "opt in" feature in your plugin? Opt in to what?

We started to collect telemetry from users who are willing to share some data with us, like WooCommerce, WordPress and PHP versions, or the shop language:

 <details>
 <summary>image (Click to expand)</summary>

 ![Telemetry](_media/telemetry.png)
 </details>

This will help us to better prioritize our development roadmap for the plugin. For example we’ve been working on translations recently and didn’t know which ones would be the most important ones (the ones with the highest user count). Unfortunately the wordpress.org repository doesn’t provide us much data about that.  

Also we will invest more time to build even more useful features and possibly add some pro features too.

If you wish to help us on this way, you can opt in, but it is absolutely voluntary and won’t change how the plugin works in any way. 

### The number of conversions counted in Google Ads are less than what's actually reported in my shop. Why?

There's a number of reasons.

1. Google Ads only counts conversions that have been triggered by an ad. 
2. The conversion window of Google Ads is typically 30 days (can be customized). That means Google Ads only counts conversions of clicks that happened during that time. 
3. If you compare Google Ads to Google Analytics, you also will not see the same numbers, as both have a different standard approach on measuring conversions: https://support.google.com/analytics/answer/2679221

### What if a user refreshes the the thankyou page multiple times, does it recount? How do you handle duplication?

We also transmit the transaction id to Google Ads. This helps Google Ads to deduplicate all conversions that have been transmitted more than once. 

This process doesn't run immediately in Google Ads but over a period of several hours after the conversion. So it might happen, that you will see a recent conversion duplicated but then fixed a few hours later. 