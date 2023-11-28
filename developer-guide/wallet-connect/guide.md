---
icon: book
order: 1000
---

# Guide


## Include Bloom in Web3Modal


### Add Bloom to wallets

As we're waiting for WalletConnect to approve our project, you can add Bloom manually to the list of wallets as follows:

```
createWeb3Modal({
  //...
  desktopWallets: [
    {
        id: '652df0cee82d5cd3cadfd57829c5578a',
        name: 'Bloom Wallet',
        links: {
            native: 'bloom://walletConnect/connect'
            universal: 'bloomwallet.io',
        },
    },
  ],
  walletImages: {
    652df0cee82d5cd3cadfd57829c5578a: "bloomwallet.io/assets/logos/bloom.png",
  };
})
```


### Add Bloom as recommendation

`WalletConnect`s `Web3Modal` has many suggestions on wallets on all ecosystems, but these suggestions can be adapted and changed by the dApp developer. If `Bloom` wallet implements features that your app requires, or if you generally want to recomment `Bloom` for your dApp's users, you can include the following code into your code base:

```
createWeb3Modal({
  //...
  featuredWalletIds: [
    '652df0cee82d5cd3cadfd57829c5578a', // Bloom wallet
  ]
})
```

If your dApp requires a feature that most of the wallets don't implement, but `Bloom` does, you can use the following code instead of the code on top:

```
createWeb3Modal({
  //...
  includeWalletIds: [
    '652df0cee82d5cd3cadfd57829c5578a', // Bloom wallet
  ]
})
```