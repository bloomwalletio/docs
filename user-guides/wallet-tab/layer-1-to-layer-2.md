---
icon: columns
order: 997
---

# Layer 1 <-> Layer 2 Transfers

### Layer 1 to Layer 2 Transfers

The following steps allow you to transfer assets from **Layer 1 to Layer 2**:

1. Initiate the send flow
2. In the select asset pop-up, you select a **Layer 1 asset** you want to transfer
3. Click on Continue
4. Select the EVM/Layer 2 Network you want to bridge to.
5. Input the Layer 2 address of the recipient.
6. Click on Continue
7. Select the amount you want to bridge
8. Click on Continue
9. Verify that the transaction details are correct
10. Click on Confirm

Behind the scenes, Bloom sends a transaction to the Shimmer EVM alias address. The transaction fills the metadata field with an encoded call to the magic contract. You can't add metadata to these kind of transactions. Additionally, a gas fee is attached to cover the execution of the smart contract.

**NFTs can be bridged in a similar way. Go to the NFT and initiate the send flow by clicking the Send button. Skip step 7 & 8.**

### Layer 2 to Layer 1 Transfers

The following steps allow you to transfer assets from **Layer 2 to Layer 1**:

1. Initiate the send flow
2. In the select asset pop-up, you select a **Layer 2 asset** you want to bridge
3. Click on Continue
4. Select the Layer 1 Network.
5. Input the Layer 1 address of the recipient.
6. Click on Continue
7. Select the amount you want to bridge
8. Click on Continue
9. Verify that the transaction details are correct
10. Click on Confirm

Upon confirmation, Bloom will send an EVM transaction that calls the magic contract. The transaction triggers a Layer 1 transaction from the ShimmerEVM committee to your Layer 1 address with the specified assets.

**NFTs can be bridged in a similar way. Go to the NFT and initiate the send flow by clicking the Send button. Skip step 7 & 8.**