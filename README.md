# Creating a Token

This is a program written in sollidity to create a token. It allows the user to mint(create) and burn(delete) tokens

## Description

This program is contract is written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. This contract represents a token with the following features:

- Token Name: "CANDY"
- Token Abbreviation: "CND"

The contract includes a `mapping` variable named `balances`, which keeps track of the token balance of each address.

The contract also includes two functions:

1. Mint Function
   - This function is used to mint (create) new tokens and assign them to the specified       address. It takes the address(to which the minted tokens will be assigned) and amount of tokens(to be added to the address) as parameters.
   - It ncreases the total token supply and updates the balance of the specified address.

2. Burn Function
   - This function is used to burn(remove) tokens from a specified address. It takes the address(from which the tokens will be removed) and amount of tokens(to be removed to the address) as parameters.
   - It decreases the total token supply and updates the balance of the specified address if the address has sufficient tokens to burn.

## Getting Started

An online Solidity IDE like [Remix](https://remix.ethereum.org/) can be used to run this program.


### Deployment and Interaction

1. Open [Remix](https://remix.ethereum.org/) in your web browser.

2. Create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., token.sol).

3. Copy and paste the provided "MyToken" contract code into the file.

4. To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.20" (or another compatible version), and then click on the "Compile token.sol" button.

5. Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "token" contract from the dropdown menu, and then click on the "Deploy" button.

6. Once the contract is deployed, you can interact with it by calling the `mint` and `burn` functions. Click on the "token" contract in the left-hand sidebar, and then click on the desired function. Enter the required parameters (address and data), and then click on the "transact" button to execute the function and update the token balances.

```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.20;

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

contract token {

    // public variables here
    string public TokenName = "CANDY";
    string public TokenAbbrv = "CND";
    uint public TotalSupply = 500;
    
    // mapping variable here
    mapping(address=>uint) public balances;
    
    // mint function
    function mint(address _adr, uint _num) public{
        TotalSupply +=_num;
        balances[_adr] += _num;
    }

    // burn function
        function burn(address _adr, uint _num) public{
            if(balances[_adr]>=_data){
        TotalSupply -=_num;
        balances[_adr] -= _num;
            }
    }
}
```


## Authors

Siddhartha A K
@siddhark1303@gmail.com

Siddhartha A K

## License

This project is licensed under the MIT License

