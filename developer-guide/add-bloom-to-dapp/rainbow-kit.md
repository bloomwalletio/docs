---
order: 800
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
1. Create a `bloomWallet.ts(|js)` file:

<details><summary>bloomWallet.ts</summary>

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
  name: 'Bloom',
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
</details>
<br/>

2. In the file where you setup your connectors, add the following:


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