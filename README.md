# 311551044-BDAF-Lab5


## This is Token Contract

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract AlanToken is ERC20, ERC20Burnable, Ownable {
    constructor() ERC20("AlanToken", "ALT") {
        _mint(msg.sender, 1000 * 10**decimals());
    }

    function decimals() public pure override returns (uint8) {
        return 18;
    }

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }
}
```
