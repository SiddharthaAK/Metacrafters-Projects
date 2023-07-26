# MyToken Solidity Contract

This repository contains a simple token contract named "MyToken" written in Solidity. The contract demonstrates basic functionalities for creating and managing a custom token on the Ethereum blockchain. If you're interested in developing your own ERC-20 compatible tokens on Ethereum, this contract can serve as a starting point.

## Description

The "MyToken" contract is written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. This contract represents a basic ERC-20 token with the following features:

- Token Name: "CANDY"
- Token Symbol/Abbreviation: "CND"
- Total Supply: 500

The contract includes a `mapping` variable named `balances`, which keeps track of the token balance of each address.

The contract also includes two functions:

1. **Mint Function**
   - Function Signature: `function mint(address _adr, uint _data) public`
   - Purpose: Allows the contract owner to mint (create) new tokens and assign them to a specified address.
   - Parameters:
     - `_adr`: The address to which the minted tokens will be assigned.
     - `_data`: The amount of tokens to be minted and added to the address's balance.
   - Behavior: Increases the total token supply and updates the balance of the specified address.

2. **Burn Function**
   - Function Signature: `function burn(address _adr, uint _data) public`
   - Purpose: Allows the contract owner to burn (remove) tokens from a specified address.
   - Parameters:
     - `_adr`: The address from which the tokens will be burned.
     - `_data`: The amount of tokens to be burned.
   - Behavior: Decreases the total token supply and updates the balance of the specified address if the address has sufficient tokens to burn.

## Getting Started

### Prerequisites

To interact with the "MyToken" contract, you need the following:

- [Remix](https://remix.ethereum.org/): An online Solidity IDE for compiling and deploying smart contracts.

### Deployment and Interaction

1. Open [Remix](https://remix.ethereum.org/) in your web browser.

2. Create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol).

3. Copy and paste the provided "MyToken" contract code into the file.

4. To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

5. Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

6. Once the contract is deployed, you can interact with it by calling the `mint` and `burn` functions. Click on the "MyToken" contract in the left-hand sidebar, and then click on the desired function. Enter the required parameters (address and data), and then click on the "transact" button to execute the function and update the token balances.

Please note that in a real-world scenario, you would need to deploy this contract on the Ethereum mainnet or a testnet to interact with it using real addresses and Ethereum gas.

```
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
    string public TokenName = "CANDY";
    string public TokenAbbrv = "CND";
    uint public TotalSupply = 500;
    
    // mapping variable here
    mapping(address=>uint) public balances;
    
    // mint function
    function mint(address _adr, uint _data) public{
        TotalSupply +=_data;
        balances[_adr] += _data;
    }

    // burn function
        function burn(address _adr, uint _data) public{
            if(balances[_adr]>=_data){
        TotalSupply -=_data;
        balances[_adr] -= _data;
            }
    }
}
```


## Authors

Siddhartha A K

## License

This project is licensed under the MIT License - see the LICENSE.md file for details

