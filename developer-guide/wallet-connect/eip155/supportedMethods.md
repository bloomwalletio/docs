---
order: 999
---

# Supported Methods

### personal_sign
The sign method calculates an Ethereum specific signature with: `sign(keccak256("\x19Ethereum Signed Message:\n" + len(message) + message))`.

By adding a prefix to the message makes the calculated signature recognizable as an Ethereum specific signature. This prevents misuse where a malicious DApp can sign arbitrary data (e.g. transaction) and use the signature to impersonate the victim.

Note See ecRecover to verify the signature.

#### Parameters
message, account

`DATA`, N Bytes - message to sign.
`DATA`, 20 Bytes - address.

#### Returns
`DATA`: Signature

#### Example

```
// Request
{
  "id": 1,
  "jsonrpc": "2.0",
  "method": "personal_sign",
  "params":["0xdeadbeaf","0x9b2055d370f73ec7d8a03e965129118dc8f5bf83"],
}

// Result
{
  "id": 1,
  "jsonrpc": "2.0",
  "result": "0xa3f20717a250c2b0b729b7e5becbff67fdaef7e0699da4de7ca5895b02a170a12d887fd3b17bfdce3481f10bea41f45ba9f709d39ce8325427b57afcfc994cee1b"
}
```


### eth_sign
The sign method calculates an Ethereum specific signature with: `sign(keccak256("\x19Ethereum Signed Message:\n" + len(message) + message))`.

By adding a prefix to the message makes the calculated signature recognizable as an Ethereum specific signature. This prevents misuse where a malicious DApp can sign arbitrary data (e.g. transaction) and use the signature to impersonate the victim.

Note the address to sign with must be unlocked.

#### Parameters
account, message

`DATA`, 20 Bytes - address.
`DATA`, N Bytes - message to sign.
#### Returns
`DATA`: Signature

#### Example

```
// Request
{
  "id": 1,
  "jsonrpc": "2.0",
  "method": "eth_sign",
  "params": ["0x9b2055d370f73ec7d8a03e965129118dc8f5bf83", "0xdeadbeaf"],
}


// Result
{
  "id": 1,
  "jsonrpc": "2.0",
  "result": "0xa3f20717a250c2b0b729b7e5becbff67fdaef7e0699da4de7ca5895b02a170a12d887fd3b17bfdce3481f10bea41f45ba9f709d39ce8325427b57afcfc994cee1b"
}
```

An example how to use solidity ecrecover to verify the signature calculated with eth_sign can be found here. The contract is deployed on the testnet Ropsten and Rinkeby.
