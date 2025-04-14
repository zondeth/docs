# Security Model

### 5.1 Trust Minimization

- All assets are either **locked in contract** or **burned**
- Relayer cannot mint or unlock without event proof
- Contracts will be open-sourced and audited

### 5.2 Quantum Resistance

- Zond-side contracts enforce XMSS or Dilithium signature verification
- All interactions with Zond include post-quantum signature proofs

### 5.3 Replay Protection

- Nonce-based event identifiers prevent double-minting
- Zond and EVM block headers included in proof for validation