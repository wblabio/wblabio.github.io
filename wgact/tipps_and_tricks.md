## Tipps and Tricks

### Add more Google Ads conversion IDs and conversion labels

In case you are using more than one Google Ads account to target your shop, this is for you. 

In order to be able to track traffic and conversions within all accounts, there are two approaches. 

1. Create a Google Ads manager account and link all Google Ads accounts for that shop under that Google Ads manager account. Once done, create a conversion pixel within the new Google Ads manager account. It is a shared pixel for all subaccounts and will track all traffic and conversions for those subaccounts. 

[Create a Google Ads manager account](https://support.google.com/google-ads/answer/7459399)

2. Add more conversion pixels to the output of the plugin with the following code. 

<!-- [LABEL](https://gist.github.com/alewolf/d49a788da470de69dc9c6bc60fbef352 ':include :type=code') -->

[add conversion identifiers to the Google Ads pixel output](https://gist.githubusercontent.com/alewolf/d49a788da470de69dc9c6bc60fbef352/raw/wgact_conversion_identifiers.php ':include :type=code')