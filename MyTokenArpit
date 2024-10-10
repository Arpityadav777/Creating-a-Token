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
