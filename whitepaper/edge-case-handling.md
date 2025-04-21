# Edge‑Case Handling

- **Unclaimed ETH (Bob offline):** After `T₁`, Alice refunds automatically; ZND she already claimed is irreversible, creating Bob‑loss scenario. Education + UI warnings essential.

- **Chain Re‑orgs:** HTLC enforces minimum confirmations (e.g., 12 ETH blocks, 20 Zond blocks) before mirror step may proceed.

- **Dust Swaps:** Contracts enforce minimum trade size (`minSwap = 0.01 ETH / 50 ZND`) to keep fee ratio sane.

- **Gas Spikes:** Front‑end suggests `T₂`/`T₁` values based on live gas oracle; `Δ` increases during congestion.
