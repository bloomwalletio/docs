---
icon: question
order: 400
---

# FAQ

## Overview

Welcome to the FAQ!

Here you will find answers to all of the frequently asked questions we have received.

:::info
If you still find yourself with questions after looking through the ones below, please reach out to us on [Discord](https://t.co/uovp2LDwKg){target=_blank}.
:::

## Setup

...

## Security

- **Can I use my Ledger device with Bloom?**

  Yes! Bloom supports creating hwardware profiles with Ledger Nano devices, however it does **NOT** support bluetooth functionality.

- **Can I use a mnemonic phrase with Bloom?**

  Yes, Bloom supports 12- and 24-word mnemonic phrases, which are used to create software profiles.

- **What is Stronghold?**

  Stronghold is the software security mechanism we use to securely store the private keys for software profiles. It is a software library that uses special cryptographic techniques to hide secrets in memory.

- **Can I change my Stronghold password?**

  Yes, you have the ability to change your Stronghold password. Navigate to the settings, click on "Security" in the sidebar to view specific security-related settings, which contains the setting to change your Stronghold password.

- **Can I use the mnemonic phrase from my Ledger device to setup a Stronghold profile in Bloom?**

  Yes, you can use the same mnemonic phrase in a Bloom software profile that is used in a Ledger hardware device, **although it is highly recommended NOT to do so**. Doing this would undermine the purpose of having a hardware wallet.

## Profiles, Accounts, & Activities

- **What is a profile / account / activity?**

  In Bloom, the top-most level structure is the "profile". Profiles contain multiple "accounts", which themselves each contain one address per network / chain. When you interact with a network or chain, an "activity" is created as a historical record of the action you performed, which would be sending a regular transaction or signing arbitrary smart contract data.

- **Will my funds disappear if I delete a profile or account?**

  Your funds will disappear in that Bloom will no longer show them in your wallet dashboard. Your funds still exist after deleting a profile or account, however it's recommended to transfer funds to another account if you do not wish to leave funds sitting unused.

- **Can I change my profile PIN?**

  Yes, you can change your profile PIN. Simply navigate to the settings, click on "Security" in the sidebar to view the security-settings, which contains setting to change your profile PIN.

### Wallet

- **How can I see my ERC20 tokens?**

  Bloom automatically tracks ERC20 tokens associated with your accounts' EVM addresses. If for some reason there is a token not showing in your portfolio, click the menu icon in the top right of the portfolio tab, which should a reveal a menu. Click the option to import an ERC20 token, which will display a popup to select a network and input a token address.

### Collectibles

*Coming soon...*

### Governance

*Coming soon...*

## Networks

- **What networks does Bloom support?**

  Bloom currently supports Shimmer (including Testnet) and Shimmer EVM (including Testnet EVM).

- **Can I connect to a custom EVM network?**

  We do **NOT** currently support connecting to custom EVM chains.

- **Will Bloom support IOTA 2.0?**

  Yes, we plan on supporting IOTA 2.0 as it progresses throughout its testing and staging phases.

## Troubleshooting

- **Bloom is not able to connect and / or interact with my Ledger device. What can I do?**

  There are a few possibilities as to what may be causing the issue for you. It is likely that you have a different app (e.g. Ledger Live) or browser extension (e.g. MetaMask) running that also interacts with your Ledger device or don't have a fully functioning USB cable.

  If the problem persists, try reading the [official help article](https://support.ledger.com/hc/en-us/articles/115005165269-Fix-USB-connection-issues-with-Ledger-Live?support=true){target=_blank} from Ledger.

- **I forgot my Ledger device PIN. How do I recover my device?**

  If you have forgotten your Ledger device PIN and are no longer able to unlock the device, you will have to restore it from an existing mnemonic. This is why it's important to backup your seed / mnemonic phrase on "analog" cold storage.

- **I forgot my Stronghold password. How can I gain access to my funds?**

  If you have forgotten your Stronghold password, there is no way to gain access to your private keys that were stored. **Always backup your Stronghold password in a reliable place.**

- **I forgot my profile PIN. How can I login to my profile?**

  You are **NOT** able to login to a profile without the correct PIN, however you can simply restore a profile using a mnemonic, Stronghold backup, or Ledger device.

## Misc

- **Can I buy tokens like IOTA and Shimmer directly in Bloom?**

  Bloom does **NOT** currently support in-app methods of purchasing IOTA nor Shimmer tokens. However, it is in our roadmap to integrate a fiat on-ramp so you may have the ability to buy tokens in-app.

- **Can I use Bloom on my mobile device?**

  Bloom is **NOT** currently available on any mobile platforms, however we have plans to develop and maintain a mobile app once the team has sufficiently expanded.

- **What is a deep link?**

  Deep links are ways for other apps or web pages to invoke functionality exposed from an app in a standardized way. Bloom supports deep links to do various things such as sending transactions, tracking tokens, etc.

- **What does Early Access mean?**

  "Early Access" is simply a term we are using to describe software that is in a functionally and visually releasable state but has **NOT** yet been audited. Once we have audited our code (available to see on [GitHub](https://github.com/bloomwalletio/bloom){target=_blank}) we will come out of Early Access into a normal "Production" stage.
