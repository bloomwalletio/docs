---
icon: book
order: 1000
---

# Guide


## Include Bloom in Web3Modal


# Web3Modal


```
createWeb3Modal({
  //...
  featuredWalletIds: [
    '652df0cee82d5cd3cadfd57829c5578a', // Bloom wallet
  ]
})
```

### Temporary

As we're waiting for WalletConnect to approve our project, you can add Bloom manually to the list of wallets as follows:

```
createWeb3Modal({
  //... 
  customWallets: [
      {
          id: 'bloom',
          name: 'Bloom',
          homepage: 'https://bloomwallet.io/',
          image_url: 'https://bloomwallet.io/assets/logos/bloom.png',
          desktop_link: 'bloom://dapps/connect/wc?uri=',
      },
  ],
})
```


# RainbowKit


```
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