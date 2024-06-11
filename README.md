# MyToken

This Solidity contract defines a basic token with mint and burn functions, allowing for the creation and destruction of tokens. The contract also keeps track of the total supply of tokens and the balance of each address.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. This contract enables the creation of a custom cryptocurrency token, allowing the owner to mint new tokens and increase the total supply, as well as burn existing tokens to reduce the supply. Additionally, it maintains a record of each user's token balance, enabling the tracking of token ownership and transfer.
## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

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

    string public tokenName="SaurabhMishra";
    string public tokenAbbre="Misau";
    uint public totalSupp=500;

    // mapping variable here

    mapping (address=>uint) public balance;
    
    // mint function
    
    function mint(address _address, uint _value) public {
        totalSupp+= _value;
        balance[_address]+= _value;
    }

    // burn function

    function burn(address _address, uint _value) public{
        if(balance[_address]>=_value){
            totalSupp-= _value;
            balance[_address]-= _value;
        }
    }

}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.26" (or another compatible version), and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "myToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the sayHello function. Click on the "myToken" contract in the left-hand sidebar, and then click on the "mint" function pass the required parameter(in this case "address" and "value") similarly for "burn" function. Finally interact with variables and change in there coressponding values.

## Authors

Saurabh Mishra  


## License

This project is licensed under the MIT License
