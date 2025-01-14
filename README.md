## Make your own Groestlcoin-payable Twitter Bot with Lightning Charge!

### Create a Wordpress site

Create a store site at https://wordpress.com/
You will need a Business plan to set up a store.

OR, create a free self-hosted Wordpress site with https://wordpress.org 

#### Install WooCommerce and Lightning Payments plugins

The WooCommerce plugin is hosted in Wordpress.

<img src="https://raw.githubusercontent.com/elaineo/lightningbot/master/docs/wp_plugins.png" width="400">

Download the Lightning Payments plugin here: https://github.com/Groestlcoin/woocommerce-gateway-lightning

Follow the instructions on the Woocommerce-Gateway repo to add Lightning as a payment option on your WooCommerce site.

#### Add a Product to your store

<img src="https://github.com/elaineo/lightningbot/blob/master/docs/product.png" width="400">

### Get a Lightning node set up

Set up groestlcoind, c-lightning, and lightning-charge. 
Instructions for all that stuff here: https://github.com/groestlcoin/lightning-charge#getting-started

### Set up a Twitter bot

#### Create a Twitter account

Go through the usual account creation process. You will need to add a mobile number to use the API.
Go to https://apps.twitter.com/. Create a new app, and copy the API keys.

#### Set up the Lightning-Twitter relay

That's this repository here.
```
git clone https://github.com/elaineo/lightningbot
cd lightningbot
npm install
```

Add Twitter API keys to environment variables in the `.env` file.

Run the relay: 
``` 
npm run start 
```

### Connect your WooCommerce payments to the Twitter bot

Create two new webhooks: One for order creation, and one for order updates.

<img src="https://github.com/elaineo/lightningbot/blob/master/docs/woocommerce.png" width="400">

Fill in your own server URL in the webhooks. The endpoints should go to `/create` and `/update`. Make sure the port number matches the one set in `.env`.

<img src="https://github.com/elaineo/lightningbot/blob/master/docs/webhook.png" width="300">

That's it! Now people can buy tweets from your bot!

