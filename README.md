


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
// it is a special identifier used in Solidity source files to specify the license under which the contract code is released.
pragma solidity ^0.8.8;
//This pragma directive specifies the version of the Solidity compiler
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

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.8;

// This contract is for a basic token system
contract MyContract {

    // Public variables for token details
    string public Token_name;
    string public Token_abbrv;
    uint256 public Total_supply;

    // Mapping of addresses to token balances
    mapping(address => uint256) public balances;

    // Constructor to initialize the contract with token details and initial supply
    constructor(string memory _name, string memory _symbol, uint256 _initialSupply) {
        Token_name = _name;
        Token_abbrv = _symbol;
        Total_supply = _initialSupply;
        balances[msg.sender] = _initialSupply;
    }

    // Function to mint new tokens, increasing total supply and balance of the specified address
    function mint(address _to, uint256 _amount) public {
        Total_supply += _amount;
        balances[_to] += _amount;
    }

    // Function to burn tokens, decreasing total supply and balance of the specified address
    function burn(address _from, uint256 _amount) public {
        require(balances[_from] >= _amount, "Insufficient balance to burn");
        Total_supply -= _amount;
        balances[_from] -= _amount;
    }
}
 
```
* To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar or you can simply click ctrl+S in windows as it is the shortcut for compiling this code or you can click cmd+S if you have mac os . Make sure the "Compiler" option is set to "0.8.8" (or another compatible version), and then click on the "Compile Mytoken.sol" button.
* Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "mytoken" contract from the dropdown menu, and then you have to put the values of tokenAbbrv , totaSupply and tokenName and then click on the "Deploy" button.





## License

This project is licensed under the [MIT] License.
