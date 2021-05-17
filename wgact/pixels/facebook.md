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

> This is a feature only available for users of the Pro version. Get the Pro version [here](https://woopt.com/).

?> The Facebook Conversion API (CAPI) is Facebook's server side event reporting mechanism. It complements the browser pixel and helps to measure events that under certain circumstances can get lost by the browser pixel. Since accurate event reporting is helpful for campaign optimization, Facebook CAPI is an important tool for performance marketers. You'll find more info about CAPI in the official documentation [here](https://developers.facebook.com/videos/2020/conversion-api-capi-external-implementation/) and [here](https://developers.facebook.com/docs/marketing-api/conversions-api/).

?> Using the Facebook Conversion API (CAPI) will increase the load on your server. Regular Facebook pixel implementations don't require interaction with the shop server on every Facebook event. The browser sends all of those directly to Facebook. But, the Facebook Conversion API is different. In addition to every browser API call each event (AddToCart, ViewItem, Purchase, etc.) has also to be sent by the shop server to the Facebook servers. This leads to a significantly higher load on the server. If you're required to use the Facebook Conversion API and your server comes to its limits (increased rate of server errors) then you will have to upgrade your server capacity. 

### Setting up Facebook CAPI

1. Get a Facebook CAPI access token: [instruction](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)

2. Paste the access token into the advanced section for Facebook within the plugin. 

Once the access token has been saved into the configuration, Facebook CAPI is active. 

### User Transparency Settings

> By default our plugin sends the minimum required amount of data to Facebook with each CAPI hit. Also the plugin doesn't process anonymous visitors. Those are visitors who block the Facebook pixel and where no `fbp` cookie is set. (Read more about the `fbp` cookie [here](https://developers.facebook.com/docs/marketing-api/conversions-api/parameters/fbp-and-fbc/)). You can change those settings in accordance with your shop policy and the laws under which your shop has to operate. 

- **Process anonymous hits**: Our plugin doesn't send a CAPI hit if a visitor is blocking the Facebook pixel. If you enable this setting our plugin will send an anonymized CAPI hit to Facebook. It will generate a random `fbp` ID and a random `user_agent`, which are the required parameters for a valid CAPI hit. 

- **Send additional visitor identifiers**: When this option is enabled, our plugin will additionally send several visitor identifiers to Facebook, such as IP address, shop ID and email. It is optional and will increase the likelihood that Facebook will match the hit to an existing Facebook user profile. For security reasons our plugin will hash the data where possible. More info about hashing and visitor identifiers [here](https://developers.facebook.com/docs/marketing-api/audiences/guides/custom-audiences/#example_sha256) and [here](https://developers.facebook.com/docs/marketing-api/conversions-api/parameters/customer-information-parameters).

### Testing

In order to test the events using the [Test Events Tool](https://developers.facebook.com/docs/marketing-api/conversions-api/using-the-api/#testEvents) our plugin offers a simple filter. Add it to your functions.php file while you're testing. 

?> The `test_event_code` can suddenly change. So make sure to double check if the right one is set for each testing session. 

```php
add_filter('wooptpm_facebook_capi_test_event_code', function () {
    // exchange TEST12345 with the test event code generated in your account
    return 'TEST12345';  
});
```

In case you suspect that something is wrong with the API call to the Facebook server, or you simply want to see the response from the Facebook server, the following filter is for you. It will output the API request response into the WooCommerce log file for Facebook CAPI. You can view the log file under WooCommerce > Status >  Logs > wooptpm-facebook-capi. Or you can open the file on the server. It is saved under /wp-content/uploads/wc-logs/.

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


