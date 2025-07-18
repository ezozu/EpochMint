# EpochMint: Decentralized NFT Marketplace with On-Chain Royalties

EpochMint provides a fully decentralized NFT marketplace solution built on Ethereum, emphasizing on-chain royalty enforcement via custom ERC-721 contracts and verifiable off-chain metadata aggregation. It provides a robust platform for creators to mint, list, and sell their NFTs while ensuring they receive royalties on secondary sales, all secured by the blockchain.

## Detailed Description

EpochMint addresses the growing need for transparent and reliable royalty mechanisms within the NFT ecosystem. Many existing marketplaces rely on centralized systems or unenforceable agreements for royalty payments. EpochMint tackles this issue by embedding royalty logic directly within the ERC-721 smart contracts. This ensures that a percentage of each secondary sale is automatically and irrevocably transferred to the original creator. We leverage the ERC-2981 standard, but enhance it with custom logic for increased flexibility and control over royalty distribution.

Beyond on-chain royalties, EpochMint features verifiable off-chain metadata aggregation. NFT metadata, containing crucial information like artwork descriptions and properties, is often stored off-chain due to cost considerations. EpochMint uses a decentralized storage solution (IPFS in our default implementation) coupled with cryptographic hashing and on-chain verification to ensure the integrity and authenticity of this metadata. This prevents manipulation and guarantees that users are interacting with genuine NFT assets.

The platform is designed with a modular architecture, allowing for future extensibility and integration with other decentralized applications (dApps). Its intuitive user interface, built with React and leveraging web3 libraries, provides a seamless experience for both creators and collectors. EpochMint fosters trust and transparency within the NFT space by prioritizing decentralization, verifiable data, and automated royalty enforcement.

## Key Features

*   **On-Chain Royalty Enforcement:** Implements ERC-2981 with custom extensions within the ERC-721 contracts, guaranteeing automated royalty payments to creators on every secondary sale. Royalties are specified as a percentage during the minting process and are enforced by the smart contract logic.
*   **Verifiable Off-Chain Metadata Aggregation:** Utilizes IPFS for decentralized storage of NFT metadata. The hash of the metadata is stored on-chain and can be verified to ensure data integrity and prevent tampering. A resolver contract allows for dynamic updates to metadata locations while maintaining immutability of previous versions.
*   **Customizable ERC-721 Contracts:** Offers a template for ERC-721 contracts that can be easily customized with unique token properties and functionalities. Includes features like minting restrictions, whitelists, and burn mechanisms.
*   **Decentralized Listing and Trading:** Enables users to list and trade NFTs directly on the marketplace without relying on intermediaries. Orders are executed through smart contracts, ensuring transparent and secure transactions.
*   **Flexible Payment Options:** Supports multiple payment tokens beyond Ether (ETH), allowing users to buy and sell NFTs using various ERC-20 tokens. The platform includes a swap mechanism to facilitate token conversions if needed.
*   **Secure Wallet Integration:** Integrates with popular web3 wallets like MetaMask, allowing users to securely connect to the platform and manage their digital assets. Utilizes signature verification for secure off-chain order signing.

## Technology Stack

*   **TypeScript:** Used for developing both the smart contracts and the front-end application, ensuring type safety and code maintainability.
*   **Solidity:** Used for writing the smart contracts that govern the NFT marketplace, including the ERC-721 contract, the marketplace contract, and the resolver contract.
*   **Hardhat:** Used as a development environment for compiling, testing, and deploying the smart contracts. Hardhat provides features like local network simulation and contract verification.
*   **React:** Used for building the user interface of the NFT marketplace, providing a responsive and interactive experience.
*   **Web3.js/Ethers.js:** Used for interacting with the Ethereum blockchain from the front-end application, enabling users to connect their wallets and execute transactions.
*   **IPFS (InterPlanetary File System):** Used for storing NFT metadata in a decentralized and immutable manner.
*   **Node.js:** Used for running the development server and building the front-end application.

## Installation

1.  **Clone the repository:**
    git clone https://github.com/ezozu/EpochMint.git
    cd EpochMint

2.  **Install dependencies:**
    npm install

3.  **Install Hardhat globally:**
    npm install -g hardhat

4.  **Compile smart contracts:**
    npx hardhat compile

5.  **Start a local Ethereum network (e.g., using Hardhat Network):**
    npx hardhat node

6.  **Deploy smart contracts to the local network:**
    npx hardhat run scripts/deploy.ts --network localhost

7.  **Start the front-end application:**
    cd client
    npm install
    npm start

## Configuration

*   **Environment Variables:**
    Create a `.env` file in the root directory of the project and define the following variables:
    *   `REACT_APP_NETWORK_ID`: The ID of the Ethereum network to connect to (e.g., 31337 for Hardhat Network).
    *   `REACT_APP_CONTRACT_ADDRESS`: The address of the deployed marketplace contract.
    *   `REACT_APP_NFT_CONTRACT_ADDRESS`: The address of the deployed ERC-721 contract.
    *   `REACT_APP_IPFS_GATEWAY`: The IPFS gateway URL to use for retrieving metadata (e.g., `https://ipfs.io/ipfs/`).

*   **Hardhat Configuration:**
    The `hardhat.config.ts` file contains settings for the Hardhat development environment, including network configurations and compiler settings.

## Usage

The front-end application provides a user-friendly interface for interacting with the NFT marketplace. Users can connect their wallets, browse NFTs, list NFTs for sale, and purchase NFTs. The application interacts with the smart contracts via web3.js/ethers.js.

Example: Minting a new NFT:

First, the user interacts with the front-end, providing details like image hash on IPFS, name, and description.

The front-end application then calls the `mint` function on the ERC-721 contract:



The `tokenURI` parameter is the IPFS URI of the NFT metadata.

Similarly, listing an NFT involves calling the `listItem` function on the marketplace contract:



## Contributing

We welcome contributions to EpochMint! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Write clear and concise code with thorough comments.
4.  Test your changes thoroughly.
5.  Submit a pull request with a detailed description of your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/ezozu/EpochMint/blob/main/LICENSE) file for details.

## Acknowledgements

We would like to thank the developers of Solidity, Hardhat, React, web3.js/ethers.js, and IPFS for creating the tools and technologies that made this project possible. We also acknowledge the contributions of the open-source community to the NFT ecosystem.