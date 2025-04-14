# System Components

### 4.1 Zond Smart Contracts

- `lockZND(address evmRecipient, uint256 amount)`
  - Locks native ZND
  - Emits lock event with proof
- `unlockZND(address zondUser, uint256 amount, bytes signature)`
  - Relayer unlocks ZND after verifying EVM-side burn
- Compatible with Dilithium or XMSS-based address formats

### 4.2 EVM Smart Contracts

#### a) wZND Token (ERC-20)
- Minted only when ZND is locked on Zond
- Burned before ZND can be unlocked
- Audited and immutable

#### b) Bridge Contract
- `mintWZND(address to, uint256 amount, bytes zondProof)`
- `burnWZND(uint256 amount)`
- Verifies relayer proofs from Zond lock events

#### c) On-Chain Orderbook DEX
- `placeOrder(isBuy, amountZND, priceETH)`
- `matchOrder(orderId)`
- `cancelOrder(orderId)`
- Fully decentralized, no off-chain matching

### 4.3 Relayer (Node.js)

- Listens to Zond and EVM events
- Submits proofs (Zond → EVM or vice versa)
- Signs unlock requests with trusted validator key
- Can be decentralized via multisig/MPC later