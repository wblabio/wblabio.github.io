# Google Ads

## Create a new conversion in Google Ads

?> Skip this step, if you've already created a purchase conversion in Google Ads

1. Open Conversions in Google Ads

    <details>
    <summary>image (Click to expand)</summary>

    ![Google Ads browse to conversions](../_media/google-ads-browse-to-conversions.png)
    </details>

2. Initiate a new conversion creation

    <details>
    <summary>image (Click to expand)</summary>

    ![Google Ads initiate new conversion creation](../_media/google-ads-create-new-conversion-initiate.png)
    </details>

3. Choose conversion type "Website"

    <details>
    <summary>image (Click to expand)</summary>

    ![Google Ads conversion type](../_media/google-ads-choose-conversion-type.png)
    </details>

4. Configure the Google Ads conversion settings

 Use the following default settings. Only change if you know what you're doing. 

 - Category: Purchase
 - Conversion name: Purchase
 - Value: Use different values for each conversion
 - Default value: zero
 - Count: Every
 - Attribution: Position-based

  <details>
  <summary>image (Click to expand)</summary>

  ![Google Ads conversion settings](../_media/google-ads-conversion-settings.png)
  </details>

## Configure the plugin

1. Get the conversion id and conversion label

 Open the purchase conversion in Google Ads.

 <details>
  <summary>image (Click to expand)</summary>

 ![Google Ads open the conversion](../_media/google-ads-open-the-conversion.png)
  </details>

 Copy the purchase conversion id and label from the Google Tag Manager tab.

 <details>
  <summary>image (Click to expand)</summary>

 ![Google Ads copy conversion id and label](../_media/google-ads-copy-conversion-id-and-label.png)
  </details>


 2. Set the conversion id and label in the plugin
<details>
  <summary>image (Click to expand)</summary>

 ![Google Ads paste conversion id and label](../_media/google-ads-paste-conversion-id-and-label.png)
  </details>


## Dynamic Remarketing

?> Requirement: In order for the dynamic remarketing to work, you need to either upload your products into the Google Merchant Center, or upload a custom business feed into your Google Ads account. 

1. Go the the beta section of the plugin and enable Dynamic Remarketing
2. Check your Product Identifier setting and adjust if necessary. **The product identifier must match the product identifiers that have been uploaded to the Google Merchant Center.**