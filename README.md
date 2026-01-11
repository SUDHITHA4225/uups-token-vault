#  TokenVault — Production-Grade UUPS Upgradeable Smart Contracts

A **production-ready upgradeable Token Vault protocol** implemented using the **UUPS (Universal Upgradeable Proxy Standard)** pattern with **Solidity**, **Hardhat**, and **OpenZeppelin Upgradeable Contracts**.

This project demonstrates **secure contract upgradeability**, **storage layout safety**, **role-based access control**, and **state preservation across upgrades**, following best practices used by real-world DeFi protocols.

---

##  Key Features

-  UUPS proxy pattern (EIP-1822)
-  Safe multi-version upgrades (V1 → V2 → V3)
-  Storage layout integrity with gaps
-  Secure initializer & reinitialization protection
-  Role-based access control (Admin, Upgrader, Pauser)
-  Comprehensive unit, upgrade, and security tests
-  Production-grade upgrade flow scripts

---

##  Repository Structure

├── contracts/
│ ├── TokenVaultV1.sol
│ ├── TokenVaultV2.sol
│ ├── TokenVaultV3.sol
│ └── mocks/
│ └── MockERC20.sol
├── test/
│ ├── TokenVaultV1.test.js
│ ├── upgrade-v1-to-v2.test.js
│ ├── upgrade-v2-to-v3.test.js
│ └── security.test.js
├── scripts/
│ ├── deploy-v1.js
│ ├── upgrade-to-v2.js
│ └── upgrade-to-v3.js
├── hardhat.config.js
├── package.json
├── submission.yml
└── README.md

---

##  Tech Stack

- **Solidity** `^0.8.20`
- **Hardhat**
- **OpenZeppelin Contracts Upgradeable**
- **Ethers.js**
- **Chai / Mocha**

---

##  Installation & Setup

### Prerequisites
- Node.js **v18 or v20** (recommended)
- npm

### Install dependencies
npm install

### Compile Contracts
npx hardhat compile

### Run Tests
npx hardhat test

## Test Coverage Includes
- Core V1 functionality
- V1 → V2 upgrade validation
-  V2 → V3 upgrade validation
-  ecurity & access-control checks
- Storage layout consistency checks
All required tests pass successfully.

---

### Deployment & Upgrade
- npx hardhat run scripts/deploy-v1.js --network localhost
- npx hardhat run scripts/upgrade-to-v2.js --network localhost
- npx hardhat run scripts/upgrade-to-v3.js --network localhost
The proxy address remains the same across all upgrades.

---

### Security & Upgrade Design

- Uses UUPS proxy pattern
- Initializers protected and disabled on implementations
- Role-based access control for upgrades and pausing
- Storage layout preserved across all versions

---

### Contract Versions Overview
🔹 TokenVaultV1
- Token deposits & withdrawals
- Deposit fee (basis points)
- Balance tracking
- Reinitialization protection

🔹 TokenVaultV2
- Yield rate configuration
- Linear yield accrual
- Yield claiming
- Deposit pause/unpause
- Backward compatible with V1

🔹 TokenVaultV3
- Withdrawal request + delay
- Time-locked withdrawal execution
- Emergency withdrawal
- Full preservation of V2 state

---

### submission.yml

The repository includes a mandatory submission.yml file defining:
- Dependency installation
- Compilation command
- Test execution command
- This enables automated evaluation without manual configuration.

---

## Summary
This project demonstrates a secure, upgradeable smart contract architecture with real-world upgrade scenarios.
It is designed to meet production and audit-level standards for upgradeable protocols.

