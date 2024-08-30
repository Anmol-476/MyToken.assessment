# MyToken
**Simple overview of use/purpose.**
This project is a Solidity smart contract designed for creating and managing a basic token on the Ethereum blockchain. It allows users to mint new tokens, burn existing ones, and track balances. The contract serves as a straightforward introduction to token management in blockchain development.

## Description:
The MyToken smart contract provides fundamental functionalities for token creation and management. It includes features that allow users to mint tokens, thereby increasing the total supply, and burn tokens, which reduces the total supply. Additionally, it tracks the total supply and individual balances of all token holders. Written in Solidity, this contract is ideal for educational purposes and for developers who want to understand the basics of token operations on Ethereum.

## Getting Started
### Installing
**How/Where to Download Your Program:**
To interact with this smart contract, you will use Remix, an online IDE for Solidity development.

**Modifications to Files/Folders:**
No modifications are required to the files or folders, but you may customize the token name and abbreviation by editing the state variables within the contract.

### Executing the Program
To run the MyToken smart contract, start by accessing the Remix IDE. Open your web browser and navigate to Remix IDE. Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension, such as MyToken.sol.

Next, copy and paste the Solidity code provided into the newly created file. This code defines the MyToken contract with functions for minting and burning tokens, along with tracking token balances.

 solidity
Code
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {
    string public tokenName = "MyToken";
    string public tokenAbbrv = "MTK";
    uint public totalSupply = 0;

    mapping(address => uint) public balances;
    function mint(address _to, uint _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    function burn(address _from, uint _value) public {
        require(balances[_from] >= _value, "Insufficient balance to burn tokens");
        totalSupply -= _value;
        balances[_from] -= _value;
    }
}
```

Once you have pasted the code, proceed to compile it. Click on the "Solidity Compiler" tab in the left-hand sidebar. Ensure the compiler version is set to 0.8.18 (or another compatible version), and then click on the "Compile MyToken.sol" button to compile the code.

After successfully compiling the contract, it's time to deploy it. Click on the "Deploy & Run Transactions" tab in the left-hand sidebar. From the dropdown menu, select the MyToken contract, and then click the "Deploy" button to deploy the contract to the blockchain.

Once deployed, you can interact with the contract's functions such as mint, burn, and check balances directly within Remix.

**Help**:
If you encounter any issues or have questions during the execution, consider the following:

Compiler Errors: Verify that your Solidity version matches the one specified in the contract (0.8.18).
Insufficient Balance Error: Ensure that the address you are trying to burn tokens from has a sufficient balance to perform the burn operation.
In Remix, while there is no specific help command, you can refer to the "Solidity Compiler" and "Deploy & Run Transactions" tabs for guidance on errors and usage. These sections provide helpful information on resolving common issues that may arise during contract execution.

**Authors**:
Anmol
Contact:thakuranmol993@gmail.com
**License**:
This project is licensed under the MIT License - see the LICENSE.md file for details.

