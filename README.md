----------------------------------------------------
**TOKENIZED STOCK MARKET SYSTEM USING BLOCKCHAIN**
----------------------------------------------------

//Our project focuses on the tokenization of shares to enhance accessibility and reduce transaction costs for stock market investors. 

//By leveraging blockchain technology, we aim to create a decentralized platform that allows users to trade fractional shares of assets, making investing more affordable and inclusive for retail investors.


## Overview
This project is a **decentralized tokenization platform** built with Solidity, designed to allow companies to create, issue, and trade their own ERC-20 tokens. It includes an integrated **marketplace** where users can buy and sell tokens in exchange for Ether. The project supports flexible token management features, including minting, burning, and managing Ether balances. The marketplace also facilitates **price discovery** and **automated token trades** through buy/sell order matching.

## Features
- **Company Tokenization**: Companies can easily tokenize their business by creating their own ERC-20 tokens.
- **Minting and Burning**: Dynamic supply management by minting and burning tokens, controlled by the MotherContract.
- **Buy/Sell Order System**: Users can place buy and sell orders for company tokens, with automated order matching.
- **Ether Transactions**: The contract accepts and handles Ether, enabling seamless token purchases and withdrawals.
- **Price Conversion Utility**: A built-in function converts between Ether and token amounts for accurate pricing.
- **Security**: Utilizes Solidity best practices, including **OpenZeppelin's** libraries for secure token and access control.

## Project Architecture

### Contracts:
- **CompanyToken**: ERC-20 token contract representing each company. Provides minting, burning, and Ether management features.
- **MotherContractAndMarketplace**: Central contract that facilitates the creation of new companies, the management of their tokens, and the marketplace for trading those tokens.

### Workflow:
1. **Deploy the MotherContractAndMarketplace**: The central contract to manage all tokenized companies.
2. **Create a Company**: The `create_company()` function deploys a new ERC-20 token with an initial supply and price.
3. **Token Trading**: Users can buy or sell tokens through the marketplace by interacting with the functions `placeBuyOrder()` and `placeSellOrder()`.
4. **Minting & Burning**: The contract owner can mint or burn tokens for a company based on business needs.

### Gas Optimization
- Functions have been optimized to avoid **infinite gas issues** in Remix and ensure efficient gas usage during large-scale transactions and order executions.
- The use of **require** statements, minimal state changes, and optimized loops ensures reduced gas consumption.

## Installation & Setup

### Prerequisites
- **Solidity**: `^0.8.0` or later
- **Node.js** and **npm** for project dependencies (if using Hardhat or Truffle)
- **MetaMask** or any Ethereum-compatible wallet for contract interaction
- **OpenZeppelin Contracts** (ERC-20, Ownable)


## Functions

### CompanyToken Contract
- **mint_tokens**: Mints new tokens for the company (only accessible by the MotherContract).
- **burn_tokens**: Burns tokens from the company's supply.
- **getEtherBalance**: Retrieves the current Ether balance held by the company’s contract.
- **withdrawEther**: Withdraws Ether earned from token sales.

### MotherContractAndMarketplace Contract
- **create_company**: Deploys a new company-specific ERC-20 token contract.
- **mint_company_tokens**: Mints additional tokens for a specific company.
- **placeBuyOrder**: Users place a buy order for company tokens using Ether.
- **placeSellOrder**: Users place a sell order to sell tokens back to the marketplace.
- **convertEtherToToken**: Calculates the price conversion between Ether and tokens for a specific company.

## Testing

For running tests, you can use frameworks like **Hardhat** or **Truffle**:
1. Write test cases to simulate buy/sell orders, token minting, and Ether withdrawals.
2. Run tests using:
    ```bash
    npx hardhat test
    ```

## Roles in the Project
The following roles have been defined to manage and develop the project:

1. **Product Analyst**: Oversees the project scope and business requirements. Other possible titles: Business Analyst, Project Sponsor.
2. **Scrum Master**: Ensures the project is running smoothly, managing workflow and solving issues within the team.
3. **Blockchain Developers**: Implement the smart contracts and integrate the tokenization features with the marketplace.
4. **Testers**: Conduct thorough testing of the smart contracts to ensure security and functionality.
5. **UI/UX Designer**: (Optional) Creates a user-friendly frontend interface for interacting with the smart contracts.

## Example Usage

```solidity
// Deploy the MotherContract
MotherContractAndMarketplace mother = new MotherContractAndMarketplace();

// Create a company token
mother.create_company("YourCompany", "YTC", 100000, 0.01 ether);

// Place a buy order
mother.placeBuyOrder(0, 100);

// Place a sell order
mother.placeSellOrder(0, 50);
```

## Contribution Guidelines

Contributions are welcome! Feel free to:
- Submit issues with bug reports or feature requests.
- Fork the repo and create pull requests for new features or improvements.

## License
This project is licensed under the **MIT License**. Please see the [LICENSE](./LICENSE) file for details.

## Contact
For questions or feedback, please contact **bhavithranravi@gmail.com**

---
