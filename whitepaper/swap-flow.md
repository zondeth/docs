# Swap Flow

## Scenario A – Alice Swaps ETH → ZND

| Step | Actor  | Chain | Action                                                                                      |
|------|--------|-------|---------------------------------------------------------------------------------------------|
| 1    | Alice  | ETH   | Generate secret `S`, compute `H`. Call `lock{value: ETH}` with `H`, Bob’s ETH address, `T₁`. |
| 2    | Bob    | ETH   | Poll or subscribe to `Locked(H, Alice)` event.                                            |
| 3    | Bob    | Zond  | Mirrors swap: calls `lockZond(H, AliceZondAddr, T₂)`.                                     |
| 4    | Alice  | Zond  | Verifies mirror; calls `claim(S)` to receive ZND, revealing `S` on‑chain.                  |
| 5    | Bob    | ETH   | Reads `S` from Zond event; calls `claim(S)` to receive ETH.                                |
| 6    | Anyone |       | After expiry, unpaid HTLCs can invoke `refund()`.                                         |

**Scenario B** (Bob swaps ZND → ETH) is symmetrical with roles inverted.
