# Facebook

## Find the pixel ID

Follow this guide by Facebook [Create and install a Facebook pixel](https://www.facebook.com/business/help/952192354843755?id=1205376682832142)

## Implemented events

Facebook event            | e-commerce | WooCommerce | implemented 
---                       | ---        | ---         | ---
**Add payment info**      | ✔️          | ✔️           | 
**Add to cart**           | ✔️          | ✔️           | ✔️
**Add to wishlist**       | ✔️          | ✔️           | ✔️
**Complete registration** |            |             |
**Contact**               |            |             |
**Customise product**     |            |             |
**Donate**                |            |             |
**Find location**         |            |             |
**Initiate checkout**     | ✔️          | ✔️           | ✔️
**Lead**                  |            |             |
**Purchase**              | ✔️          | ✔️           | ✔️
**Schedule**              |            |             |
**Search**                | ✔️          | ✔️           | ✔️
**Start trial**           |            |             |
**Submit application**    |            |             |
**Subscribe**             |            |             |
**View content**          | ✔️          | ✔️           | ✔️

The AddPaymentInfo event has not been implemented since in a standard WooCommerce setup there is no save button or next step before hitting the purchase button. Hitting the purchase button **is** the next step, and the event that we want to track. 


## Facebook Conversion API (CAPI)

> Available in version 1.10 and above

> This is a feature only available for users of the Pro version. Get the Pro version [here](https://woopt.com/)

?> The Facebook Conversion API (CAPI) is Facebook's server side event reporting mechanism. It complements the browser pixel and helps to measure events that under certain circumstances can get lost by the browser pixel. Since accurate event reporting is helpful for campaign optimization, Facebook CAPI is an important tool for performance marketers. You'll find more info about CAPI in the official documentation [here](https://developers.facebook.com/videos/2020/conversion-api-capi-external-implementation/) and [here](https://developers.facebook.com/docs/marketing-api/conversions-api/).

### Setting up Facebook CAPI

1. Get a Facebook CAPI access token: [instruction](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)

2. Paste the access token into the advanced section for Facebook within the plugin. 

Once the access token has been saved into the configuration, Facebook CAPI is active. 

### User Transparency Settings

> By default our plugin sends the minimum required amount of data to Facebook with each CAPI hit. Also the plugin doesn't process anonymous visitors. Those are visitors who block the Facebook pixel and where no `fbp` cookie is set. (Read more about the `fbp` cookie [here](https://developers.facebook.com/docs/marketing-api/conversions-api/parameters/fbp-and-fbc/)). You can change those settings in accordance with your shop policy and the laws under which your shop has to operate. 

- **Process anonymous hits**: Our plugin doesn't send a CAPI hit if a visitor is blocking the Facebook pixel. If you enable this setting our plugin will send an anonymized CAPI hit to Facebook. It will generate a random `fbp` ID and a random `user_agent`, which are the required parameters for a valid CAPI hit. 

- **Send visitor IP address**: When this option is enabled, our plugin will additionally send the visitor's IP address to Facebook. It is optional and will increase the likelihood that Facebook will match the hit to an existing Facebook user profile.

- **Send visitor email**: When this option is enabled, our plugin will additionally send the visitor's email address to Facebook. It will only do this where the email is available, like for logged in users and past buyers. Also the email will not be sent in plain text but [hashed](https://developers.facebook.com/docs/marketing-api/audiences/guides/custom-audiences/#example_sha256). This setting is optional and will increase the likelihood that Facebook will match the hit to an existing Facebook user profile.

- **Send visitor shop ID**: When this option is enabled, our plugin will additionally send the visitor's shop ID address to Facebook (the WooCommerce user ID of that visitor). It will only do this where the shop ID is available for that visitor, like for logged in users and past buyers. Also the shop ID will not be send in plain text but [hashed](https://developers.facebook.com/docs/marketing-api/audiences/guides/custom-audiences/#example_sha256). This setting is optional and will increase the likelihood that Facebook will match the hit to an existing Facebook user profile.

### Testing

In order to test the events using the [Test Events Tool](https://developers.facebook.com/docs/marketing-api/conversions-api/using-the-api/#testEvents) our plugin offers a simple filter. Add it to your functions.php file while you're testing. 

?> The `test_event_code` can suddenly change. So make sure to double check if the right one is set for each testing session. 

```php
add_filter('wooptpm_facebook_capi_test_event_code', function () {
    // exchange TEST12345 with the test event code generated in your account
    return 'TEST12345';  
});
```

In case you suspect that something with the API call to the Facebook server is wrong, or you simply want to see the response from the Facebook server, the following filter is for you. It will output Facebook's response into the regular log file (you'll need to [enable logging](https://codex.wordpress.org/WP_DEBUG) for that). 

```php
add_filter('wooptpm_send_http_api_facebook_capi_requests_blocking', '__return_true');
```

### Data Processing Options

> Data Processing Options are a way to control how the the data is used in the Facebook systems and better support shop owners with their California Consumer Privacy Act (CCPA) compliance efforts. You'll find more information in the official [documentation](https://developers.facebook.com/docs/marketing-apis/data-processing-options).

The following filter is a simple way to add the necessary fields to each CAPI hit. Below settings are just an example. You need to make sure that you are using settings which are inline with your shops policy regarding CCPA. 

```php
add_filter('wooptpm_facebook_capi_data_processing_options', function () {
    return [
        'data_processing_options'         => ['LDU'],
        'data_processing_options_country' => 1,
        'data_processing_options_state'   => 1000,
    ];
}, 10, 2);
```


