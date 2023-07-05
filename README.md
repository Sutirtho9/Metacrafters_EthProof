# My token
This Solidity program is a token contract that allows minting and burning of tokens. It serves as a basic example for understanding the functionality of token contracts using the Solidity programming language.

# Requirements
1.The contract will have public variables to store details about the token (Token Name, Token Abbreviation, Total Supply).

2.The contract will have a mapping of addresses to balances (address => uint256) to keep track of token balances.

3.There will be a mint function that takes two parameters: an address and a value. This function will increase the total supply by the given value and add the value to the balance of the sender's address.

4.The contract will include a burn function that works the opposite of the mint function. It will take an address and a value, deduct the value from the total supply, and subtract the value from the balance of the sender's address.

5.The burn function will include conditionals to ensure that the balance of the sender is greater than or equal to the amount to be burned.

# Getting Started
Prerequisites To compile and interact with this contract, you need the following: 
1.Solidity compiler (version 0.8.18) 
2.Ethereum development environment (e.g., Remix, Truffle, Hardhat)

# Compilation
Copy the code from the code block below

# Code
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public TokenName = "BigCoin";
    string public TokenAbbrv = "BGC";
    uint public TotalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balance;

    // mint function
    function mint(address _address, uint _value) public{
       TotalSupply += _value;
       balance[_address] += _value;

    } 

    // burn function
    function burn (address _address, uint _value) public{
       if(balance[_address]>=_value){
        TotalSupply -=_value;
        balance[_address]-=_value;  
       }
    }

}
```
2.Paste the code into your Solidity development environment.

# Deployment and Usage
Compile the contract using the Solidity compiler (version 0.8.18). Deploy the compiled contract to an Ethereum network of your choice. Interact with the contract using the following functions: mint(address Address, uint256 value): Mints new tokens by increasing the total supply and adding the specified value to the balance of the specified address. burn(address Address, uint256 value): Burns tokens by deducting the specified value from the total supply and subtracting it from the balance of the specified address. The function includes a conditional check to ensure that the balance of the sender is greater than or equal to the value being burned.

# Authors
Sutirtho Chakravorty
sutirthochakravorty@gmail.com

# License
This project is licensed under the MIT License. See the LICENSE.md file for details.
