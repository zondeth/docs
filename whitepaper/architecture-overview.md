# Architecture Overview

```plaintext
User <--> Zond Smart Contract (ZND Lock) <--> Node.js Relayer <--> EVM Smart Contracts (wZND + Orderbook)
```

**Bridge Flow (ZND → ETH):**

1. User locks ZND on Zond → emits Lock event
2. Relayer listens → submits proof to EVM
3. wZND is minted on EVM chain

**Bridge Flow (ETH → ZND):**

1. User sends ETH to DEX contract and buys wZND
2. Burns wZND → emits Burn event
3. Relayer listens → unlocks ZND on Zond
