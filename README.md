# EpochMint: Decentralized Time-Based Token Issuance

EpochMint is a TypeScript-based framework for creating and managing tokens that are automatically minted and distributed based on predefined time intervals, known as epochs. This system simplifies the process of implementing time-lock release strategies, recurring payments, and other time-dependent token mechanisms within decentralized applications. EpochMint provides a flexible and secure solution for developers looking to integrate time-based token functionality into their projects, eliminating the need for complex custom scripting and enhancing the reliability of time-sensitive token operations.

EpochMint addresses the challenge of securely and predictably managing token issuance over time in decentralized environments. Traditional methods often rely on centralized servers or require complex smart contracts to handle time-based events. EpochMint shifts this responsibility to a verifiable and transparent on-chain system, ensuring consistent and auditable token distribution. By decoupling token creation from manual intervention, EpochMint reduces the risk of human error and ensures the fair and equitable distribution of tokens according to a pre-defined schedule. This leads to a more trustworthy and reliable system, particularly beneficial for projects requiring long-term commitment and consistent token supply management.

This repository provides the core EpochMint framework, including modules for epoch configuration, token management, and distribution logic. It offers a set of interfaces and classes that can be easily integrated into existing smart contracts or utilized as a standalone solution. EpochMint is designed to be highly modular, allowing developers to customize the epoch length, token distribution rate, and other parameters to suit their specific needs. Furthermore, the framework incorporates robust error handling and security measures to prevent unauthorized token issuance or manipulation, ensuring the integrity of the entire system.

## Key Features

*   **Configurable Epoch Length:** Define the duration of each epoch using a Unix timestamp, providing granular control over the timing of token issuance. This can be configured during initial setup using the `EpochConfig` interface and updated through designated administrative functions.
*   **Automatic Token Minting:** The system automatically mints tokens at the end of each epoch based on a pre-defined issuance rate. The minting logic is encapsulated in the `EpochMintService` class and is triggered by an on-chain event tied to the epoch end.
*   **Flexible Token Distribution:** Distribute newly minted tokens to designated recipients based on configurable allocation rules. The framework supports different distribution strategies, including proportional allocation, weighted distribution, and direct transfer to specific addresses.
*   **Secure Access Control:** Implement granular access control mechanisms to restrict administrative functions to authorized users. Access control is managed through a role-based system, allowing for separation of duties and preventing unauthorized modification of epoch configurations.
*   **Event-Driven Architecture:** Leverage a comprehensive set of events to track epoch transitions, token minting, and distribution activities. These events provide valuable insights into the system's operation and facilitate integration with external monitoring tools.
*   **TypeScript-Based Development:** Built with TypeScript, providing type safety, enhanced code maintainability, and improved developer productivity. The use of TypeScript ensures that the code is well-structured and easy to understand.
*   **Comprehensive Unit Testing:** Includes a suite of unit tests to ensure the reliability and correctness of the core functionalities. The test suite covers various scenarios, including epoch transitions, token minting, and distribution logic, providing confidence in the system's stability.

## Technology Stack

*   **TypeScript:** A statically typed superset of JavaScript that provides enhanced type safety, code organization, and developer productivity.
*   **Node.js:** A JavaScript runtime environment that enables the execution of TypeScript code on the server-side.
*   **npm (Node Package Manager):** A package manager for installing and managing project dependencies.
*   **ethers.js:** A comprehensive JavaScript library for interacting with the Ethereum blockchain and its ecosystem.
*   **Mocha:** A JavaScript testing framework used for writing and running unit tests.
*   **Chai:** An assertion library used for verifying the expected behavior of the code during testing.
*   **Solidity (optional):** While the core logic is in TypeScript, integration with smart contracts may require Solidity for on-chain interactions.

## Installation

1.  Clone the repository:
    `git clone https://github.com/ezozu/EpochMint.git`
2.  Navigate to the project directory:
    `cd EpochMint`
3.  Install dependencies:
    `npm install`

## Configuration

EpochMint relies on environment variables for configuration. Create a `.env` file in the project root directory and define the following variables:

*   `NODE_ENV`: Specifies the environment (e.g., `development`, `production`).
*   `RPC_URL`: The URL of the Ethereum RPC endpoint.
*   `PRIVATE_KEY`: The private key of the administrator account. (Use a dedicated test key for development)
*   `TOKEN_ADDRESS`: The address of the token contract to be managed (if applicable).
*   `EPOCH_LENGTH`: The desired length of each epoch in seconds (e.g., `86400` for one day).
*   `ISSUANCE_RATE`: The number of tokens to mint per epoch.

Example `.env` file:

NODE_ENV=development
RPC_URL=http://localhost:8545
PRIVATE_KEY=0x... (your private key)
TOKEN_ADDRESS=0x... (token contract address)
EPOCH_LENGTH=86400
ISSUANCE_RATE=1000

## Usage

First, instantiate the `EpochMintService` class:



To start the epoch minting process:



You can also manually trigger a token minting and distribution:



The `EpochMintService` class provides methods for retrieving the current epoch, checking if an epoch has ended, and configuring token distribution rules. Refer to the source code for detailed API documentation.

## Contributing

We welcome contributions to EpochMint! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Write clear and concise commit messages.
4.  Submit a pull request with a detailed description of your changes.
5.  Ensure that your code adheres to the project's coding standards and includes comprehensive unit tests.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/ezozu/EpochMint/blob/main/LICENSE) file for details.

## Acknowledgements

We would like to thank the open-source community for their invaluable contributions to the technologies used in this project.