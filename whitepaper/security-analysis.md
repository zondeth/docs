# Security Analysis

| Threat                         | Mitigation                                                                                              |
|--------------------------------|---------------------------------------------------------------------------------------------------------|
| Secret interception            | Secret revealed only after both parties locked funds; interception merely expedites Bob’s claim.       |
| Replay / double‑spend          | `H` identifies unique swap; contract state machine forbids reuse.                                      |
| Timelock griefing              | `T₂ < T₁` ensures counter‑party has `Δ ≥ block‑time` margin.                                            |
| Quantum key theft (ETH side)   | Exposure window ≤ `T₁`; choose `T₁` such that QC cracking within this timeframe is infeasible today.      |
| Contract bugs                  | Multiple audits                                                                                        |
