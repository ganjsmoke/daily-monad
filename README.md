
# Auto Daily Monad

This repository provides a script to automate interaction with Ethereum-based smart contracts, including deposit, staking, swapping, and more. The script runs on the Monade testnet and is designed to interact with various decentralized finance (DeFi) contracts.

## Features

- **Deposit**: Automatically deposits a random amount of MON tokens.
- **Swap**: Executes token swaps on Uniswap, Izumi, and other decentralized exchanges (DEX).
- **Stake and Unstake**: Stake or unstake MON tokens on Kintsu and Magma contracts.
- **Multicall Execution**: Executes multiple contract interactions in a single transaction for efficiency.
- **Wallet Processing**: Randomly selects functions to execute on multiple wallets in a loop, ensuring automated transactions.
- **Logging**: Detailed logs are generated for each transaction executed.

### Recommended Requirements

- **Testnet MON**: It's recommended to have at least 5-10 MON tokens in your account.
- **Staked MON**: You should already have staked MON tokens on the Magma contract for unstaking actions.
  
### Clone and Setup

1. **Clone the Repository**

   First, clone the repository to your local machine:

   ```bash
   git clone https://github.com/ganjmsoke/daily-monad.git
   cd daily-monad
   ```

2. **Install Dependencies**

   Install all the required dependencies:

   ```bash
   npm install
   ```

3. **Setup the Wallet File**

   Create a file called `private_keys.txt` in the root directory. This file should contain the private keys for the wallets you want to use, one private key per line. Make sure to keep this file secure.


4. **Run the Script**

   After setup, you can start the script by running the following command:

   ```bash
   node index.js
   ```

   The script will start processing wallets and executing functions in a loop. It will continuously run until manually stopped.

### Functions and Their Descriptions

The following functions are implemented:

1. **DepositApriori**: Randomly deposits a small amount of MON tokens to the specified contract address.
2. **depositMagma**: Deposits MON tokens to the Magma contract.
3. **swapUniswap**: Executes a token swap using the Uniswap router.
4. **stakeKintsu**: Stakes a random amount of MON tokens on the Kintsu contract.
5. **unstakeMagma**: Unstakes a portion (5-7%) of the staked MON tokens from the Magma contract.
6. **swapIzumi**: Executes token swap using the Izumi router.
7. **swapBean**: Executes ETH-to-token swaps on a different contract.

Each of these functions will execute transactions, and there are randomized delays between each transaction to simulate a natural flow.

### Logging

The script includes a logger that outputs the status of each action:

- **Success**: When a transaction is successfully executed.
- **Error**: When an error occurs during transaction execution.
- **Info**: General information about the ongoing process.
- **Warning**: Warnings about specific actions that might require attention.

Example log:
```
[16:30:22] [0x...12345] [swapUniswap] Successfully swapped 0.05 ETH for tokens.
```

### Notes

- Make sure the Ethereum addresses provided in the `private_keys.txt` file have sufficient MON and ETH for transaction fees.
- The Monade testnet is used for the execution, so ensure you're working with testnet tokens and not real funds.

### License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
