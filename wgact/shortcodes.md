# Shortcodes

> In order to be able to track leads as conversions, the plugin provides shortcodes. They need to be added to the thankyou pages to which lead forms redirect to after a form submission. 


## Examples


`[conversion-pixel pixel="google-ads" gads-conversion-label="abcdefg"]`

`[conversion-pixel pixel="facebook"]`

`[conversion-pixel pixel="facebook" fbc-event="Schedule"]`

`[conversion-pixel pixel="twitter"]`

`[conversion-pixel pixel="twitter" twc-event="Signup"]`

`[conversion-pixel pixel="ms-ads"]`

`[conversion-pixel pixel="pinterest"]`

`[conversion-pixel pixel="pinterest" pinc-event="Signup"]`

`[conversion-pixel pixel="pinterest" pinc-event="Signup" pinc-lead-type="test-type"]`

`[conversion-pixel pixel="all" gads-conversion-label="aabbcc"]`

`[conversion-pixel pixel="all" gads-conversion-label="aabbccdd" fbc-event="Schedule" twc-event="Signup" pinc-event="Signup" pinc-lead-type="test-type"]`


## General Instructions

> The only required parameter for all use cases is `pixel`. With this parameter you can choose which conversion pixel to fire, or, if you want to fire all of them. 

`pixel="google-ads"`

`pixel="all"`

> All pixels use default parameters that can be overridden.

## Google Ads

> For each Google Ads conversion you need to set the `gads-conversion-label`. It is the only required parameter for a Google Ads lead conversion.

`[conversion-pixel pixel="google-ads" gads-conversion-label="abcdefg"]`

If you need to you can also set the `gads-conversion-id` as additional parameter. If you ommit that parameter, the plugin will automatically use the conversion ID which is set in the plugin. 

?> More information on conversion tracking you'll find on the Google Ads support pages [here](https://support.google.com/google-ads/answer/6331314) and [here](https://support.google.com/google-ads/answer/6331304)

## Facebook

> For the Facebook lead conversion shortcode there are no required parameters other than the `pixel` parameter. By default the event type is being reported as `Lead`.

`[conversion-pixel pixel="facebook"]`

In order to override the default event you can set the `fbc-event` parameter. 

`[conversion-pixel pixel="facebook" fbc-event="Schedule"]`

?> More information on events you'll find on the Facebook developer pages [here](https://developers.facebook.com/docs/analytics/send_data/events/)

## Microsoft Ads

!> This shortcode is in beta. Microsofts documentation is not very clear on some parts of how to configure a lead conversion.

> For the Mircrosoft Ads lead conversion shortcode there are no required parameters other than the `pixel` parameter. By default the event is being reported as `submit` and the event label as `lead`.

`[conversion-pixel pixel="ms-ads"]`

You can set an override all of the following parameters: 

`ms-ads-event`

`ms-ads-event-category`

`ms-ads-event-label`

`ms-ads-event-value`

?> More information on events you'll find on the Microsoft Ads developer pages [here](https://bingadsuet.azurewebsites.net/UETDirectOnSite_ReportCustomEvents.html)

## Twitter

> For the Twitter lead conversion shortcode there are no required parameters other than the `pixel` parameter. By default the event is being reported as `CompleteRegistration`.

`[conversion-pixel pixel="twitter"]`

In order to override the default event you can set the `twc-event` parameter. 

`[conversion-pixel pixel="twitter" twc-event="Signup"]`

?> More information on events you'll find on the Twitter developer pages [here](https://business.twitter.com/en/help/campaign-measurement-and-analytics/conversion-tracking-for-websites.html)

## Pinterest

> For the Twitter lead conversion shortcode there are no required parameters other than the `pixel` parameter. By default the event is being reported as `lead`.

`[conversion-pixel pixel="pinterest"]`

In order to override the default event you can set the `pinc-event` parameter. 

`[conversion-pixel pixel="pinterest" pinc-event="signup"]`

Additionally you can set the `lead-type` parameter which is empty by default:

`[conversion-pixel pixel="pinterest" pinc-event="signup" pinc-lead-type="New release promotion"]`

?> More information on events you'll find on the Pinterest developer pages [here](https://help.pinterest.com/en/business/article/add-event-codes) and [here](https://help.pinterest.com/en/business/article/track-conversions-with-pinterest-tag)