---
icon: book
order: 1000
---

# Guide

`WalletConnect`s `Web3Modal` has many suggestions on wallets on all ecosystems, but these suggestions can be adapted and changed by the dApp developer. If `Bloom` wallet implements features that your app requires, or if you generally want to recomment `Bloom` for your dApp's users, you can include the following code into your code base:

```
createWeb3Modal({
  //...
  featuredWalletIds: [
    '1ae92b26df02f0abca6304df07debccd18262fdf5fe82daa81593582dac9a369', // Bloom wallet
  ]
})
```

If your dApp requires a feature that most of the wallets don't implement, but `Bloom` does, you can use the following code instead of the code on top:

```
createWeb3Modal({
  //...
  includeWalletIds: [
    '1ae92b26df02f0abca6304df07debccd18262fdf5fe82daa81593582dac9a369', // Bloom wallet
  ]
})
```