# WinVaultTokenomics

## Overview
The WinVaultTokenomics system is a staking and reward mechanism designed to incentivize token holders to lock their tokens in a contract in exchange for reward tokens over a specified duration. This README provides an overview of the functionality and usage of the WinVaultTokenomics class and its supporting Token class.

## Components

### WinVaultTokenomics Class
This class manages the staking of tokens, calculation of rewards, and distribution of reward tokens. It includes functionalities such as staking tokens, withdrawing tokens, calculating earned rewards, and distributing rewards.

#### Attributes
- **staking_token**: The token being staked.
- **rewards_token**: The token distributed as rewards.
- **owner**: The address of the contract owner.
- **duration**: Duration of the rewards distribution period.
- **finish_at**: Timestamp when the rewards distribution period ends.
- **updated_at**: Timestamp when rewards were last updated.
- **reward_rate**: Rate at which rewards are distributed.
- **reward_per_token_stored**: Accumulated rewards per token.
- **total_supply**: Total amount of staked tokens.
- **balance_of**: Dictionary storing staked amounts for each user.
- **user_reward_per_token_paid**: Dictionary storing paid reward per token for each user.
- **rewards**: Dictionary storing earned rewards for each user.

#### Methods
- `__init__(self, staking_token, rewards_token, duration)`: Initializes the contract with the staking token, rewards token, and reward duration.
- `only_owner(func)`: Decorator to restrict functions to the contract owner.
- `update_reward(self, account)`: Updates the reward for a specific account.
- `last_time_reward_applicable(self)`: Returns the last time rewards were applicable.
- `reward_per_token(self)`: Calculates the reward per token.
- `stake(self, user, amount)`: Allows a user to stake a specified amount of tokens.
- `withdraw(self, user, amount)`: Allows a user to withdraw a specified amount of staked tokens.
- `earned(self, account)`: Calculates the earned rewards for an account.
- `get_reward(self, user)`: Allows a user to claim their earned rewards.
- `set_rewards_duration(self, duration, caller=None)`: Sets the rewards duration (owner only).
- `notify_reward_amount(self, amount, caller=None)`: Notifies the contract of the reward amount (owner only).

### Token Class
This class represents a simple ERC-20-like token used for both staking and rewards.

#### Attributes
- **name**: Name of the token.
- **total_supply**: Total supply of the token.
- **balances**: Dictionary storing balances of each account.

#### Methods
- `__init__(self, name, total_supply)`: Initializes the token with a name and total supply.
- `balance_of(self, account)`: Returns the balance of a specific account.
- `transfer(self, recipient, amount)`: Transfers a specified amount of tokens to a recipient.
- `transfer_from(self, sender, recipient, amount)`: Transfers a specified amount of tokens from a sender to a recipient.
