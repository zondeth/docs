# Smart‑Contract Specification

```solidity
function lock(bytes32 H, address recipient, uint256 expiry) payable;

function claim(bytes memory S);          // requires SHA256(S) == H

function refund(bytes32 H);                       // callable after expiry

event Locked(bytes32 indexed H, address indexed locker, uint256 amount);

event Claimed(bytes32 indexed H, address indexed claimer);

event Refunded(bytes32 indexed H, address indexed refunder);
```
