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
    'XXXXXYYYYZZZZZ11111222223333', // Bloom wallet, this ID will be fixed once we're approved
  ]
})
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
      desktop_link: "bloom://wallet-connect/connect?uri=",
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

**NOTE**

As we're waiting for RainbowKit to merge our PR in, you can add Bloom manually to the list of wallets as follows:

Create a `bloomWallet.ts(|js)` file:

```javascript
import {
  Chain,
  Wallet,
  getWalletConnectConnector,
} from '@rainbow-me/rainbowkit';

export interface MyWalletOptions {
  projectId: string;
  chains: Chain[];
}

export const bloomWallet = ({
  chains,
  projectId,
}: MyWalletOptions): Wallet => ({
  id: 'bloomWallet',
  name: 'Bloom Wallet',
  iconUrl: 'https://bloomwallet.io/assets/logos/bloom.png',
  iconBackground: '#000',
  downloadUrls: {
    windows: 'https://bloomwallet.io/',
    macos: 'https://bloomwallet.io/',
    linux: 'https://bloomwallet.io/',
    desktop: 'https://bloomwallet.io/',
  },
  createConnector: () => {
    const connector = getWalletConnectConnector({ projectId, chains });
    return {
      connector,
      desktop: {
        getUri: async () => {
          const provider = await connector.getProvider();
          const uri = await new Promise<string>(resolve =>
            provider.once('display_uri', resolve)
          );
          return `bloom://wallet-connect/connect?uri=${encodeURIComponent(uri)}`;
        }
      },
    };
  },
});
```

In the file where you setup your connectors, add the following:


```javascript
import { bloomWallet } from 'path/to/bloomWallet.ts';
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
