---
icon: book
order: 1000
---

# Guide

# Web3Modal

To include `Bloom Wallet` in the list of recommended wallets, please add the following code to your Web3Modal options:

```javascript
createWeb3Modal({
  //...
  featuredWalletIds: [
    "652df0cee82d5cd3cadfd57829c5578a", // Bloom wallet
  ],
});
```

---

**NOTE**

As we're waiting for WalletConnect to approve our project, you can add Bloom manually to the list of wallets as follows:

```javascript
createWeb3Modal({
  //...
  customWallets: [
    {
      id: "bloom",
      name: "Bloom",
      homepage: "https://bloomwallet.io/",
      image_url: "https://bloomwallet.io/assets/logos/bloom.png",
      desktop_link: "bloom://wallet-connect/connect",
    },
  ],
});
```

---

# RainbowKit

To include `Bloom Wallet` in the list of recommended wallets, please add the following code to your RainbowKit options:

```javascript
import {
  ...,
  bloomWallet,
  ...
} from '@rainbow-me/rainbowkit/wallets';


...


const connectors = connectorsForWallets([
    {
        groupName: 'Recommended',
        wallets: [
            ...,
            bloomWallet({ projectId, chains }),
            ...
        ],
    },
]);
```
