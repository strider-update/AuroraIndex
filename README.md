# AuroraIndex

Built for Base

AuroraIndex is a compact Base-oriented repository focused on validating wallet connectivity, RPC accuracy, and explorer visibility across Base environments using official Coinbase tooling.

Rather than implementing application-specific logic, AuroraIndex acts as an infrastructure checkpoint for Base Mainnet and Base Sepolia.

## Overview

This repository is intended to:
- Confirm Base network accessibility and chainId consistency
- Exercise OnchainKit wallet connection flows
- Perform deterministic, read-only onchain queries via Viem
- Provide explicit Basescan references for inspection

## Networks

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  
RPC: https://mainnet.base.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  
RPC: https://sepolia.base.org  

## Application Details

Primary file: app/auroraIndex.ts

When executed, the application:
- Initializes an OnchainKitProvider bound to the selected Base chain
- Renders wallet onboarding UI
- Uses Viem to query Base RPC endpoints for:
  - chainId
  - latest block number
  - native ETH balance for a supplied address
- Outputs Basescan explorer URLs for transparent verification

## Repository Structure

app/  
- auroraIndex.ts  
  React entry component combining wallet UX with Base JSON-RPC reads.

Typical supporting files:
- package.json
- tsconfig.json

## Tooling

OnchainKit  
Wallet UI components and Base-first primitives  
https://github.com/coinbase/onchainkit  

Viem  
EVM client for Base RPC reads  

## Installation and Usage

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies using your preferred package manager and run the project with a standard React/Vite or Next.js development server.

Optional environment variables:
- VITE_BASE_RPC_URL
- VITE_BASE_SEPOLIA_RPC_URL

## Author

GitHub: https://github.com/strider-update
Public contact (email): strider_update.0w@icloud.com
Public contact (X): https://x.com/jennifer_oj3 

## License

MIT License

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract #1 address:  
0xfef7fa067c0667feefac32926289370706f36322 

Deployment and verification:
- https://sepolia.basescan.org/address/0xfef7fa067c0667feefac32926289370706f36322
- https://sepolia.basescan.org/0xfef7fa067c0667feefac32926289370706f36322/0#code  

Contract #2 address:  
0x0215a111c44fc8976cae4d2f7207e4145a236275

Deployment and verification:
- https://sepolia.basescan.org/address/0x0215a111c44fc8976cae4d2f7207e4145a236275 
- https://sepolia.basescan.org/0x0215a111c44fc8976cae4d2f7207e4145a236275/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
