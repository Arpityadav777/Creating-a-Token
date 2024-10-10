


# Project Title

ETH-PROOF-Beginner-EVM-Course

## Description

So this is a README file so that other can understand this code more clearly.
Requirements:-
The contract has public variables to store details about the token:
Token Name,
Token Abbreviation,
Total Supply.
The contract includes a mapping to keep track of the balance of each address.
The contract has a mint function that:
Takes an address and a value as parameters.
Increases the total supply by the specified value.
Increases the balance of the specified address by the specified value.
The contract has a burn function that:
akes an address and a value as parameters.
Decreases the total supply by the specified value.
Decreases the balance of the specified address by the specified value.
Ensures that the balance of the address is greater than or equal to the value to be burned.
## Getting Started



To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:
### Executing program


```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.8;

// This contract represents a simple token management system
contract TokenContract {

    // Public state variables for token information
    string public tokenName;
    string public tokenSymbol;
    uint256 public totalSupply;

    // Mapping to keep track of token balances per address
    mapping(address => uint256) public accountBalances;

    // Constructor to initialize the token with a name, symbol, and initial supply
    constructor(string memory _tokenName, string memory _tokenSymbol, uint256 _initialSupply) {
        tokenName = _tokenName;
        tokenSymbol = _tokenSymbol;
        totalSupply = _initialSupply;
        accountBalances[msg.sender] = _initialSupply; // Assign the initial supply to contract deployer
    }

    // Function to add new tokens to an account, increases total supply
    function mintTokens(address recipient, uint256 amount) public {
        totalSupply += amount;
        accountBalances[recipient] += amount;
    }

    // Function to destroy tokens from an account, decreases total supply
    function burnTokens(address account, uint256 amount) public {
        require(accountBalances[account] >= amount, "Not enough tokens to burn");
        totalSupply -= amount;
        accountBalances[account] -= amount;
    }
}

 
```
* To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar or you can simply click ctrl+S in windows as it is the shortcut for compiling this code or you can click cmd+S if you have mac os . Make sure the "Compiler" option is set to "0.8.8" (or another compatible version), and then click on the "Compile Mytoken.sol" button.
* Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "mytoken" contract from the dropdown menu, and then you have to put the values of tokenAbbrv , totaSupply and tokenName and then click on the "Deploy" button.





## License

This project is licensed under the [MIT] License.
