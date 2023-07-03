# EthProofFinalAssessment
# MyToken - Simple Solidity Token Contract

This repository contains a simple Solidity smart contract for creating and managing a custom ERC20 token called "MyToken" (token abbreviation "MTK"). The contract provides basic functionalities to mint and burn tokens, as well as keeping track of token balances.

## Requirements

The contract must satisfy the following requirements:

1. The contract will have public variables that store the details about your coin:
   - Token Name: "MyToken"
   - Token Abbreviation: "MTK"
   - Total Supply: The initial total supply is set to 0, and it will be increased when tokens are minted.

2. The contract will have a mapping of addresses to balances:
   - bal: A mapping that associates addresses with their respective token balances.

3. The contract will have a mint function:
   - Function Signature: function mint(address _add, uint _val) public
   - Description: This function allows users to mint (create) new tokens. It takes two parameters - an address and a value. The function increases the total supply by the given value and adds the same value to the balance of the specified address.

4. The contract will have a burn function:
   - Function Signature: function burn(address _add, uint _val) public
   - Description: This function allows users to burn (destroy) tokens. It takes two parameters - an address and a value. The function deducts the specified value from the total supply and reduces the balance of the specified address by the same amount.

5. The burn function should include conditionals to ensure that the balance of the sender is greater than or equal to the amount that is supposed to be burned.

## Example Usage

Below is an example of how you can use the MyToken contract:

solidity
// Deploy the MyToken contract and get its address
MyToken myToken = new MyToken();

// Mint 100 tokens to a specific address
address recipient = 0x...; // Replace with the recipient's address
uint amountToMint = 100;
myToken.mint(recipient, amountToMint);

// Check the balance of the recipient
uint balance = myToken.bal(recipient); // The balance will be 100

// Burn 50 tokens from the recipient's balance
uint amountToBurn = 50;
myToken.burn(recipient, amountToBurn);

// Check the balance again
balance = myToken.bal(recipient); // The balance will be 50 after burning


## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
