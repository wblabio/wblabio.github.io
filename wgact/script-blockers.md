## Script Blockers

> Script blockers can cause issues when using the plugin in the backend. As as consequence the settings page can appear broken.

Everyone who is reading this article knows that our plugin's purpose is to track visitors and their actions on a WooCommerce shop. In order to achieve this our plugin injects tracking pixels provided by popular advertising platforms like Google or Facebook. 

On the other hand, ad and script blockers have emerged due to annoying ads and privacy concerns around user tracking.

Because of our plugin's purpose it was added to some privacy filter lists which are being used by some ad and script blockers. 

While this is totally fine for visitos on the front end of a shop, it can cause issues on the back end of a shop. Our plugin uses a few admin scripts in the back end in order to make the interface faster and easier to use. But if those scripts are blocked, the interface may appear broken. 

?> The simplest way to fix issues with the plugin in the WooCommerce back end, caused by script blockers, is to disable the script blocker, or whitelist the shop domain in the script blocker. 

We tested the most popular ad and script blockers with our plugin. Most of them work fine with our plugin, but some block our admin scripts. Where possible, we've whitelisted the plugin admin scripts. 

Ad or script blocker      | compatible  | whitelisted
---                       | ---         | ---
**Adblock**               | ✔️           | 
**Adblock Plus**          | ✔️           | 
**AdBlocker Ultimate**    | ❌          | 
**AdGuard AdBlocker**     | ✔️           | 
**Fair AdBlocker**        | ✔️           | 
**Ghostery**              | ✔️           | 
**uBlock Origin**         | ✔️           | ✔️



