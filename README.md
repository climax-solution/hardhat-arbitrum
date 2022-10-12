# hardhat-arbitrum

Hardhat plugin for Arbitrum Developers.

## Features

ArbitrumScan Contract Verification

## Prerequisites

Before the installation steps you need to have your hardhat project initialized using the command

```bash
npx hardhat init
```

Make sure to have dependencies installed!

## Installation

Use the following command to install

```bash
npm i hardhat-arbitrum --save-dev
```

Import the plugin in your `hardhat.config.js`:

```js
require("hardhat-arbitrum");
```

Or if you are using TypeScript, in your `hardhat.config.ts`:

```ts
import "hardhat-arbitrum";
```

Remove / Comment the import for `@nomicfoundation/hardhat-toolbox`

Add the following configuration to the `config` object in `hardhat.config.js`.

```js
networks: {
        arbitrumGoerli: {
            // can be replaced with the RPC url of your choice.
            url: "https://goerli-rollup.arbitrum.io/rpc",
            accounts: [
                "<YOUR_PRIVATE_KEY>"
            ],
        },
        arbitrumOne: {
            url: "https://arb1.arbitrum.io/rpc",
            accounts: [
                "<YOUR_PRIVATE_KEY>"
            ],
        }
    },
    etherscan: {
        apiKey: {
            arbitrumGoerli: "<OPTIMISMSCAN_API_KEY>",
            arbitrumOne: "<OPTIMISMSCAN_API_KEY>"
        },
    },
```

Verify your contracts using the following command (Make sure your contracts are compiled before verification)

Arbitrum Goerli Testnet

```bash
npx hardhat verify <CONTRACT_ADDRESS> <CONSTRUCTOR_ARGS> --network arbitrumGoerli
```

Arbitrum Mainnet

```bash
npx hardhat verify <CONTRACT_ADDRESS> <CONSTRUCTOR_ARGS> --network arbitrumOne
```
