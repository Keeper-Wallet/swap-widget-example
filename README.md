# Keeper Swap Widget

Keeper Swap Widget provides users of your website with a handy tool for exchanging tokens of the Waves ecosystem at the best price. The widget displays all exchange options and suggests the most profitable one in real time. Check the [Demos](#demos)!

By default, the widget uses built-in [Signer](https://docs.waves.tech/en/building-apps/waves-api-and-sdk/client-libraries/signer) to connect a user wallet: Keeper, Waves.Exchange, or Ledger. However, if Signer is already implemented on your website, you can pass the Signer object and the user address to the widget so the user don't have to log in twice.

What’s more, you can become our partner and receive a portion of fee from each exchange made in Keeper Swap Widget embedded in your website.

- [Earn with Keeper Swap Widget](#earn-with-keeper-swap-widget)
- [How to embed widget](#how-to-embed-widget)
- [Widget settings](#widget-settings)
- [Demos](#demos)
- [Functions](#widget-functions)

## Earn with Keeper Swap Widget

Keeper Swap Widget charges a fee for each exchange: 0.1% of the output amount. You can get a significant part of that fee. At the start, we pay 50% of fees to our partners!

How to become a partner:

1. [Fill out the form](https://forms.gle/XuWFtF2mqmMf7yoL8) to get your referral key.
2. Embed the widget on your website and specify the key as a `referrer` option when creating your widget, like this:

   ```javascript
    KeeperSwapWidget.create(/* element */, {
      referrer: 'YOUR KEY',
      // other widget settings like toAssetIds, theme etc.
    });
   ```

3. Enjoy your income!

## How to embed widget

1. Add the script to your site:

   ```html
   <script src="https://swap-widget.keeper-wallet.app/lib/swap-widget.umd.js"></script>
   ```

2. Set up the widget:

   ```javascript
    KeeperSwapWidget.create(/* element */, {
      /* widget settings */
    });
   ```
   For more examples, check out [Demos](#demos) section below.

3. The widget is ready to use!

## Widget settings

- Referrer
- Dark theme
- Initial asset pair
- List of assets to swap to: for example, you can allow users to buy the token of your project only
- User wallet: the Signer object and the user address

## Demos

- [Default layout](https://codepen.io/faergeek/pen/OJvYaMY?editors=1000)
- [Dark theme](https://codepen.io/faergeek/pen/VwXOVKG?editors=1000)
- [Initial asset pair](https://codepen.io/faergeek/pen/poLmQNb?editors=1000)
- [Assets to swap to](https://codepen.io/faergeek/pen/eYMaQvW?editors=1000)
- [One asset to swap to](https://codepen.io/faergeek/pen/RwMmqpv?editors=1000)
- [Signer and address passed](https://codepen.io/faergeek/pen/LYdoXyr?editors=1000)

## Widget functions

- `setWallet()`

  Use it to pass a user wallet to Keeper Swap Widget if Signer is implemented on your website.

  Connect the user wallet:

  ```javascript
  const signer = new window.signer.Signer();
  signer.setProvider(/* ... */);

  const widget = KeeperSwapWidget.create(/* ... */);

  widget.setWallet({
    address,
    signer,
  });
  ```

  Disconnect the user wallet:

  ```javascript
  widget.setWallet(null);
  ```

- `destroy()` is needed to remove the widget if it's no longer needed:

  ```javascript
  widget.destroy();
  ```
