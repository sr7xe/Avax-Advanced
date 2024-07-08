# ERC20 Token and Vault Contract

This repository contains the implementation of an ERC20 token named "AVAX ADVANCED" (symbol: AVAX) and a Vault contract that interacts with the token. 

## Contracts Overview

### ERC20.sol

This contract implements the ERC20 token standard.

#### Features

- `name`: The name of the token.
- `symbol`: The symbol of the token.
- `decimals`: The number of decimals the token uses.
- `totalSupply`: The total supply of the token.
- `balanceOf`: Mapping from an address to its token balance.
- `allowance`: Mapping from an address to another address and the amount allowed to be spent.
- `transfer`: Transfers a specified amount of tokens to a specified address.
- `approve`: Approves another address to spend a specified amount of tokens.
- `transferFrom`: Transfers tokens from one address to another using an allowance.
- `mint`: Creates new tokens and adds them to the total supply.
- `burn`: Destroys tokens and reduces the total supply.

#### Events

- `Transfer`: Emitted when tokens are transferred, including zero value transfers.
- `Approval`: Emitted when the allowance of a `spender` for an `owner` is set by a call to `approve`.

### IERC20.sol

This interface defines the standard functions for an ERC20 token. It is used by the Vault contract to interact with the ERC20 token.

#### Functions

- `totalSupply()`: Returns the total token supply.
- `balanceOf(address account)`: Returns the account balance of another account with address `account`.
- `transfer(address recipient, uint amount)`: Transfers `amount` tokens to `recipient`.
- `allowance(address owner, address spender)`: Returns the amount which `spender` is still allowed to withdraw from `owner`.
- `approve(address spender, uint amount)`: Allows `spender` to withdraw from the caller’s account, multiple times, up to the `amount`.
- `transferFrom(address sender, address recipient, uint amount)`: Transfers `amount` tokens from `sender` to `recipient`.

#### Events

- `Transfer`: Emitted when tokens are transferred, including zero value transfers.
- `Approval`: Emitted when the allowance of a `spender` for an `owner` is set by a call to `approve`.

### Vault.sol

This contract allows users to deposit ERC20 tokens and receive shares in return. Users can also withdraw their tokens by burning their shares.

#### Features

- `token`: The ERC20 token that the Vault contract interacts with.
- `totalSupply`: The total supply of shares in the Vault.
- `balanceOf`: Mapping from an address to its share balance.
- `deposit`: Allows users to deposit tokens and receive shares in return.
- `withdraw`: Allows users to withdraw tokens by burning their shares.

#### Functions

- `_mint(address _to, uint _shares)`: Mints shares and assigns them to an address.
- `_burn(address _from, uint _shares)`: Burns shares from an address.
- `deposit(uint _amount)`: Deposits tokens and mints shares to the sender.
- `withdraw(uint _shares)`: Burns shares and transfers the corresponding amount of tokens to the sender.

## Usage

1. **Deploy the ERC20 contract:**

   Deploy the `ERC20` contract and note the deployed contract address.

2. **Deploy the Vault contract:**

   Deploy the `Vault` contract with the address of the deployed `ERC20` contract as the parameter.

3. **Interact with the contracts:**

   - Use the `ERC20` contract to mint, transfer, and burn tokens.
   - Use the `Vault` contract to deposit tokens and receive shares, and to withdraw tokens by burning shares.
