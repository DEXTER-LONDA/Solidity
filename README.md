# Error Handling Contract

This Solidity program is a simple "mint and burn" program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to mint and burn the tokens.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. This is a contract that mint and burn the tokens.

this contract contain three public variable called "name", "symbol", and "totalSupply" and two functions "mint" and "burn" and the mapping variable "balance".

"mint" function contain two arguments "_value" and "_address". This function helps the user to add/mint token. In this function you have to provide address and the value then this function increment the totalSupply by the given value and update balance by the given value.

"burn" function contain two arguments "_value" and "_address". This function helps the user to spend/burn token. In this function you have to provide address and the value then this function has the if statement with the condition to make sure the balance of sender is greater than or equal to the amount that supposed to be burned if this condition passes it will decrement the totalSupply by the given value and update balance by the given value.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
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
    string public name="Deepak";
    string public symbol="DK";
    uint public totalSupply=0;
    // mapping variable here
    mapping(address => uint) public balances;
    // mint function
    function mint(address _address, uint _value) public {
      totalSupply += _value;
      balances[_address] += _value;
    }
    // burn function
    function burn(address _address, uint _value) public {
      if(balances[_address] >= _value){
         totalSupply -= _value;
         balances[_address] -= _value;
      }
    }
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18", and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it. Click on the "HelloWorld" contract in the left-hand sidebar, and then enter the "_address" in the "address" slot of balance and call it. Then enter address and "_value" to be minted in the "mint" function. Finally, click on the "transact" button to execute the function and then call "balance" and "totalSupply" to check the current balance and totalSupply of token.

Enter the address to "_address" and value to "_value" to be burned in the "burn" function then click on the "transact" button to execute the function and then call "balance" and "totalSupply" to check the current balance and totalSupply of token.

Call "name" and "symbol" to to check them. 
