---
icon: diamond
order: 998
---

# Governance

`bloom://governance`

## Add Proposal

`bloom://governance/addProposal`

This operation brings the user to the add proposal popup:

:::image
![](../../static/add-proposal-popup.png "Add proposal popup")
:::

The deep link structure is as follows:

```
bloom://governance/addProposal?eventId=<eventId>&nodeUrl=<nodeUrl>
```

The following parameters are **required**:

- `eventId` - the event ID of the proposal's corresponding participation event in the network

The following parameter(s) are **optional**:

- `nodeUrl` - the specific node that is tracking the proposal's corresponding participation event

:::info
If the node requires authentication (e.g. username and password, JWT), the user will be required
to manually enter the information.
:::

Example:

[!button Click me!](bloom://governance/addProposal?eventId=0x6d27606a773a3c87c151af09ad58ddc831864e2141ef598075dc24be5668ca7f7f&nodeUrl=https://api.testnet.shimmer.network)

Source:

```
bloom://governance/addProposal?eventId=0x6d27606a773a3c87c151af09ad58ddc831864e2141ef598075dc24be5668ca7f7f&nodeUrl=https://api.testnet.shimmer.network
```

<style>
  .image {
    margin: auto;
    max-width: 420px;
  }
</style>
