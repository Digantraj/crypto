# ETH Proof crypto 
## Description

The `MyToken` Solidity smart contract establishes a cryptocurrency system named "Sleeper" (`Name_of_token`). It includes public variables `Name_of_token` set to "Sleeper" and `Abb_of_token` set to "SP", denoting the token's name and abbreviation respectively. Initially, `Total_supply` starts at zero, tracking the total tokens issued. The contract employs a `balance` mapping to record token holdings for Ethereum addresses. Two key functions are provided: `minter` enables the creation of new tokens for a specified address, increasing the total supply and updating the recipient's balance. Conversely, `burner` allows tokens to be destroyed from a specified address, reducing both the total supply and the address-specific balance, contingent on sufficient token holdings. These functions collectively manage token issuance and destruction, supported by transparent variables that detail the token's identity and current supply.

# Getting Started

### Installing
*No Installation Required

### Execution of Program

* To execute the program
1. Open in Remix IDE
2. Create a new file and paste the 'MyToken' contract code into the file.
3. Compile
4. Deploy
* Contract
```cpp
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;


/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public Name_of_token = "Sleeper";
    string public Abb_of_token = "SP";
    uint public Total_supply = 0;

    // mapping variable here
    mapping(address => uint) public balance;

    // mint function
    function minter (address add, uint value) public
    {
        Total_supply += value;
           balance[add] += value;
    }

    // burn function
  function burner (address add, uint value) public
    {
           if (balance[add]>=value)
           {
           Total_supply -= value;
           balance[add] -= value;
           }
    }
}
```
## Help
If you encounter any issues or have questions regarding the contract, please feel free to open an issue in this repository or contact the authors directly.

## Authors
* Digant Raj- https://github.com/Digantraj
  
## License 
This project is licensed under the MIT License - see the LICENSE.md file for details.


