# Simple Storage with Foundry

This project demonstrates deploying and interacting with a simple Solidity smart contract (`SimpleStorage.sol`) using [Foundry](https://github.com/foundry-rs/foundry). It supports running the contract on a local Anvil node and the Alchemy chain.

## Overview

**SimpleStorage** is a basic smart contract that allows storing and retrieving a single `uint256` value. This project uses Foundry's tools to compile, test, and deploy the contract.

## Prerequisites

- [Foundry](https://github.com/foundry-rs/foundry) installed. You can install it using:
  ```bash
  curl -L https://foundry.paradigm.xyz | bash
  foundryup
  ```
- An [Alchemy](https://www.alchemy.com/) account and API key for connecting to the Ethereum network.

## Tools Used

- **Forge**: For building, testing, and deploying the contract.
- **Anvil**: A local Ethereum node for testing.
- **Cast**: For interacting with the deployed contract.

## Getting Started

### 1. Clone the Repository

```bash
git clone <repository-url>
cd <repository-folder>
```

### 2. Install Dependencies

```bash
forge install
```

### 3. Compile the Contract

```bash
forge build
```

### 4. Run Tests

```bash
forge test
```

### 5. Start a Local Anvil Node

```bash
anvil
```

### 6. Deploy the Contract Locally

Deploy the contract to the local Anvil node:

```bash
forge create --rpc-url http://127.0.0.1:8545 --private-key <your_private_key> src/SimpleStorage.sol:SimpleStorage
```

### 7. Deploy the Contract to Alchemy

Replace `<your_rpc_url>` with your Alchemy RPC URL and `<your_private_key>` with your wallet's private key:

```bash
forge script script/Counter.s.sol:CounterScript --rpc-url <your_rpc_url> --private-key <your_private_key>
```

### 8. Interact with the Contract

Use `cast` to interact with the deployed contract. For example, to call a function:

```bash
cast send <contract_address> "store(uint256)" 42 --rpc-url <your_rpc_url> --private-key <your_private_key>
```

## Project Structure

- `src/SimpleStorage.sol`: The Solidity contract.
- `script/Counter.s.sol`: Deployment script.
- `test/SimpleStorage.t.sol`: Tests for the contract.

## Resources

- [Foundry Documentation](https://book.getfoundry.sh/)
- [Alchemy Documentation](https://docs.alchemy.com/)

## License

This project is licensed under the [MIT License](LICENSE).