# ETH Assessment
### Overview
This is a simple Ethereum smart contract written in Solidity that implements the basic structure of a token. The contract includes functions to mint and burn tokens, as well as public variables for token details and a mapping to store balances for different addresses.

###  Features
1. Token Name and Abbreviation:

  + Public variables to store the name (tokenName) and abbreviation (tokenAbbrv) of the token.
  + Initially set to "META" for the name and "НТА" for the abbreviation.

2. Total Supply:

  + A public variable totalSupply keeps track of the total number of tokens in circulation.
  + Initialized to 0 at the beginning.

3. Balances Mapping:

  + A mapping that associates each Ethereum address with its token balance.
    
4. Mint Function:

  + Allows minting (creating) new tokens.
  + Increases the total supply and updates the balance of the recipient address.

5. Burn Function:
6. 
  + Allows burning (destroying) tokens.
  + Reduces the total supply and the balance of the address, but only if the address has enough tokens.
    
##  Functions
### Public Variables
```
string public tokenName = "META";
string public tokenAbbrv = "НТА";
uint public totalSupply = 0;

```
  + tokenName: Stores the name of the token (META).
  + tokenAbbrv: Stores the abbreviation of the token (НТА).
  + totalSupply: Stores the total supply of tokens. Starts at 0.

### Balances Mapping
```
mapping(address => uint) public balances;
```
  + Maps Ethereum addresses to their token balances.
### Mint Function
```
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
```
  + Purpose: Mints new tokens and assigns them to a specific address.
  + Parameters:
    +  _address: The recipient’s Ethereum address.
    +  _value: The number of tokens to mint.
  + Effect:
    + Increases totalSupply.
    + Updates the balance of the _address.
### Burn Function
```
function burn(address _address, uint _value) public {
    if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
```
+ Purpose: Burns (destroys) tokens from a specific address.
+ Parameters:
  + _address: The Ethereum address from which tokens will be burned.
  + _value: The number of tokens to burn.
+ Effect:
  + Decreases totalSupply.
  + Reduces the balance of the _address, but only if it has enough tokens.

## Author

Eleazar EL Tan 

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.






    
