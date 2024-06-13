# Token Generating 

This Solidity program is a Token Generating  program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to mint the tokens and the minted tokens could be burnt afterwards. 

## Description

This program  written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain.It includes a mint function that allows authorized accounts to generate new tokens, thereby increasing the total supply and assigning the newly created tokens to a specific address. Additionally, the contract features a burn function, which permits token holders to destroy their tokens, effectively reducing the total supply and allowing for deflationary token models or removal of tokens from circulation

## Getting Started

### Executing program

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
  string public tokenName = "PROFESSOR";
  string public tokenAbbrv = "PROF";
  uint public totalSupply = 0;

    // mapping variable here
 mapping (address=> uint) public balances;

    // mint function
function mint (address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
    // burn function
function burn (address _address, uint _value) public {
    if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
}

