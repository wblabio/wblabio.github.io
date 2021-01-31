# Google Consent Mode

## default settings

?> When enabled the default settings will be set to the maximum data privacy settings for all regions. Additional code allows consent management tools (like [cookiebot](https://www.cookiebot.com/en/google-consent-mode/)) to override settings according to visitor choice, and cookieless conversion tracking for Google Ads. 

When the Google consent mode is enabled the plugin outputs the following default consent settings:

```js
gtag('consent', 'default', {
    'ad_storage': 'denied', 
    'analytics_storage': 'denied',
    'wait_for_update': 500
    });
                
gtag('set', 'ads_data_redaction', true);
                
gtag('set', 'url_passthrough', true);
```

?> Head over to the Google consent mode information [here](https://support.google.com/google-ads/answer/10000067) or [here](https://support.google.com/analytics/answer/9976101) and the developer documentation [here](https://developers.google.com/gtagjs/devguide/consent) to learn more. 