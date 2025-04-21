# Design Goals

| Goal                   | Rationale                                                   |
|------------------------|-------------------------------------------------------------|
| Two‑Way Symmetry       | Either asset can initiate the swap.                        |
| Minimal Trust          | No third‑party signing, no liquidity escrow beyond HTLCs.   |
| Deterministic Finality | Exactly one of two outcomes: successful exchange or full refund. |
| PQ‑Aware               | Keep ZND’s PQ security intact; limit ETH exposure window.  |
