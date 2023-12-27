---
icon: link
expanded: false
order: 998
---

# Deep Linking

Deep links are special URLs that, when navigated to, open
applications rather than a website.
In our case we are interested in the user experiences that they enable
between websites, applications, platforms, etc. by providing more interoperability.

Bloom has its own deep link scheme, exposing (limited) functionality that is required in
some type of user flow. A trivial example would be a user who buys native tokens on Soonaverse and
must make a payment transaction to execute the buy order. Clicking on a deep link embedded inside the
Soonaverse platform triggers Bloom to open and auto-fill the transaction data as necessary, making it
a simple confirm and click job for the user.

:::caution
Bloom **will NEVER** automatically execute actions initiated by a deep link; they should **ALWAYS** require manual
confirmation on behalf of the user.
:::

## Scheme

The Bloom deep link scheme can be broken down to the following (simple) syntax:

```
bloom[-<stage>]://<context>/<operation>[?param=<param>]
```

The parameters are as follows:

- `stage` - indicates a specific stage of the app to target, options are:
  - `alpha` - the first available version of Bloom containing brand new features
  - `beta` - the next available version of Bloom containing new but slightly tested features
  - `laters` - the Bloom Shimmer version, containing new and well-tested features
- `context` - the part of Bloom that contains the operation, options are:
  - `wallet` - managing coins and tokens
  - `collectibles` - managing NFTs
  - `governance` - managing voting events and proposals
- `operation` - an operation within a specific context (see below for more detail)
- `param` - query parameter(s) relevant for the specified operation

If you wish to target the production version, simply omit this from the prefix:

`bloom://`
