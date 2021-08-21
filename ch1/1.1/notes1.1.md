## 1.1 Notes

We're going to start by creating a client for our centralized payment operator. A client is a piece of software that allows an end-user to interact with the network. In bitcoin and Ethereum this is a node (full client) or wallet (light client), and in the more centralized operator space the equivalent would be an app or website you use to connect to the centralized service. Here our client will alow users to send transactions to the central operator to be processed.

Inside of our client's `constructor`, assign `this.wallet` to `ETHCrypto.createIdentity()` to create a public key, private key, and Ethereum address. This will allow users to sign and receive messages with their client.



### Verifying Digital Signatures

Digital Signatures allow anyone to use someon's address to verify that they used their private key to sign a message. If someone sends us a signed message, we'd like our client to be able to verify tha ttheir signature is valid.

Write a `verify`method that takes in 3 parameters (in this order):

1. `signature` - Sender's signature
2. `message` - Hash of the sender's message
3. `sender` - Sender's Ethereum address