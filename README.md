----------------------------------------------------
**TOKENIZED STOCK MARKET SYSTEM USING BLOCKCHAIN**
----------------------------------------------------

//Our project focuses on the tokenization of shares to enhance accessibility and reduce transaction costs for stock market investors. 

//By leveraging blockchain technology, we aim to create a decentralized platform that allows users to trade fractional shares of assets, making investing more affordable and inclusive for retail investors.

## Overview
This project is a **Solidity-based platform** that allows the creation, minting, burning, and trading of company-specific ERC-20 tokens. It integrates a marketplace where users can place buy and sell orders for company tokens, and it handles Ether transactions seamlessly. The project is designed to tokenize companies, allowing them to issue and manage their tokens through an Ethereum-based smart contract.

## Key Features
- **Company Token Creation**: Deploy ERC-20 tokens for companies with an initial supply.
- **Minting & Burning**: Control token supply dynamically with minting and burning functions.
- **Buy/Sell Marketplace**: Users can place buy and sell orders for tokens at a set price in Ether.
- **Ether Transactions**: The smart contract accepts Ether, facilitating token purchases.
- **Withdraw Ether**: Company contracts can withdraw Ether earned from token sales.

## Project Architecture
- **CompanyToken Contract**: Represents a company as an ERC-20 token with minting, burning, and Ether management functionalities.
- **MotherContract and Marketplace**: Central contract to manage multiple company tokens, place buy/sell orders, and execute transactions.
- **Gas Management**: Efficient handling of gas fees for transactions on Ethereum, reducing costs.

## Prerequisites
- Solidity `^0.8.0`
- OpenZeppelin Contracts (ERC-20, Ownable)
- Ethereum-compatible development environment (e.g., [Remix](https://remix.ethereum.org), Hardhat, Truffle)
- [MetaMask](https://metamask.io) or any other Ethereum wallet for deployment and interaction.

## Getting Started

1. **Clone the repository**:
    ```bash
    git clone https://github.com/yourusername/your-repo.git
    cd your-repo
    ```

2. **Install dependencies** (if using Hardhat or Truffle):
    ```bash
    npm install
    ```

3. **Deploy Contracts**:
   - Deploy the `MotherContractAndMarketplace` contract, which acts as the main interface for creating and managing company tokens.
   - Use the `create_company` function to deploy new `CompanyToken` contracts for specific companies.

4. **Interaction with the Marketplace**:
   - **Place Buy Orders**: Purchase tokens using Ether and receive the tokens immediately if available.
   - **Place Sell Orders**: Sell your tokens by transferring them to the marketplace at the set company price.

5. **Gas Optimization**:
   - Infinite gas issues in Remix can be addressed by carefully optimizing your functions. Functions requiring large loops should be avoided, and efficient gas usage patterns are implemented for token transfers and marketplace actions.

## Smart Contract Overview

### `CompanyToken` Contract
An ERC-20 token representing a company, with additional functionality:
- **mint_tokens**: Mint new tokens (restricted to the `MotherContract`).
- **burn_tokens**: Burn tokens (restricted to the `MotherContract`).
- **withdrawEther**: Withdraw Ether from the contract (only for the contract owner).

### `MotherContractAndMarketplace` Contract
Central contract to manage company token creation and facilitate trading:
- **create_company**: Deploy a new company token.
- **mint_company_tokens**: Mint additional tokens for a specific company.
- **placeBuyOrder**: Place a buy order for company tokens.
- **placeSellOrder**: Sell tokens back to the marketplace.

## Project Roles
- **Product Owner**: Define project requirements and business logic.
- **Scrum Master**: Ensure smooth workflow and remove blockers.
- **Developers**: Implement smart contracts and handle integrations.
- **Testers**: Test the smart contracts for security and functionality.
- **UI/UX Designer**: (Optional) Create a frontend for interacting with the contracts.

## Smart Contract Deployment Example

Example for deploying and interacting using **Remix**:
```solidity
// Deploy the MotherContract
MotherContractAndMarketplace mother = new MotherContractAndMarketplace();

// Create a new company
mother.create_company("CompanyName", "CMP", 10000, 0.1 ether);

// Place a buy order
mother.placeBuyOrder(0, 50);

// Place a sell order
mother.placeSellOrder(0, 30);
```

## Contributing
Feel free to submit issues, fork the repository, and create pull requests. Contributions are always welcome!

## License
This project is licensed under the **MIT License**. See the [LICENSE](./LICENSE) file for details.

---
