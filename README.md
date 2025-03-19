# ChainSafe Vault Management System

## Overview
ChainSafe Vault Management System is a decentralized vault system designed to securely store, manage, and transfer assets on the blockchain. It provides an extensive suite of functions to handle vault creation, transfers, cancellations, disputes, security enhancements, and much more, tailored to secure asset custody.

This repository includes smart contracts for managing vaults, handling high-value transactions, implementing dispute resolution mechanisms, and integrating advanced security features such as two-factor authentication (2FA) and cryptographic transaction verification.

## Key Features

- **Vault Creation**: Create asset vaults with customizable conditions (e.g., amount, recipient, phases).
- **Asset Transfer**: Securely complete asset transfers from vaults to recipients.
- **Vault Management**: Cancel, return assets, extend vault durations, and handle expired vaults.
- **Dispute Resolution**: Dispute vaults and resolve conflicts with arbitration mechanisms.
- **Security Enhancements**: Enable 2FA and cryptographic signature verification for high-value vaults.
- **Admin Functions**: Admins can approve high-value vaults, freeze suspicious vaults, and schedule critical operations with delays.

## Contract Overview

### Key Data Structures

- **VaultStorage**: A mapping structure storing vault information, including vault state, creator, recipient, token details, and block height information.
- **current-vault-id**: A variable tracking the latest vault ID for creating new vaults.

### Core Functions

1. **Vault Lifecycle Management**:
   - Create staged vaults with customizable phases and amounts.
   - Cancel or return vault assets.
   - Extend vault durations and claim expired vaults.

2. **Dispute and Arbitration**:
   - Initiate and resolve disputes between vault participants.
   - Assign percentage splits during dispute resolution.

3. **Security Features**:
   - Add 2FA for high-value vaults.
   - Cryptographic verification of transactions and signatures.

4. **Vault State Changes**:
   - Manage vault state transitions (e.g., pending, accepted, completed, disputed, frozen, etc.).

5. **Admin Operations**:
   - Admin can schedule critical operations and manage high-value vaults with extra approval.

## Smart Contract Functions

Here are some of the key public functions:

- **create-staged-vault**: Initiate a new vault with defined phases, recipient, token, and amount.
- **complete-vault-transfer**: Complete the transfer of assets from a vault to the recipient.
- **cancel-vault**: Cancel a vault and return assets to the creator.
- **extend-vault-duration**: Extend the duration of a vault to delay expiry.
- **dispute-vault**: Start a dispute for a vault with a specified reason.
- **resolve-dispute**: Resolve a dispute by splitting assets between creator and recipient based on a percentage.
- **enable-auth-2fa**: Enable two-factor authentication for vaults above a threshold amount.
- **crypto-verify-transaction**: Verify the cryptographic signature of a transaction for a vault.

## Installation

To deploy and interact with the contracts, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/chainSafe-vault-management.git
    cd chainSafe-vault-management
    ```

2. Install dependencies (if necessary):
    - Use [Stacks CLI](https://github.com/stacksgov/stacks-blockchain) for deploying smart contracts.
    - Follow the instructions in the Stacks documentation to set up a local environment for testing or deploy to the mainnet.

3. Deploy contracts:
    ```bash
    stacks deploy
    ```

## Usage

Once the contracts are deployed, you can interact with the vault system through Stacks transactions. Below are some examples of how to use the system.

- Create a vault:
    ```bash
    stacks call-contract --contract vault-management --function create-staged-vault --args ...
    ```

- Dispute a vault:
    ```bash
    stacks call-contract --contract vault-management --function dispute-vault --args ...
    ```

- Complete a vault transfer:
    ```bash
    stacks call-contract --contract vault-management --function complete-vault-transfer --args ...
    ```

## Contributing

1. Fork the repository and clone it to your local machine.
2. Create a new branch (`git checkout -b feature-name`).
3. Make your changes and commit them (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-name`).
5. Create a pull request with a description of the changes you made.

## License

This project is licensed under the MIT License

## Contact

For questions or contributions, please open an issue or contact the repository maintainers.
