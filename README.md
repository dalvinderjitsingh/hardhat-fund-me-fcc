# Hardhat Fund Me

This is for section 7 of [Web3, Full Stack Solidity, Smart Contract & Blockchain - Beginner to Expert ULTIMATE Course | Javascript Edition](https://github.com/smartcontractkit/full-blockchain-solidity-course-js#lesson-7-hardhat-fund-me).

- [Hardhat Fund Me](#hardhat-fund-me)
- [Getting Started](#getting-started)
  - [Requirements](#requirements)
  - [Quickstart](#quickstart)
- [Usage](#usage)
  - [Testing](#testing)
    - [Test Coverage](#test-coverage)
- [Deployment to a testnet or mainnet](#deployment-to-a-testnet-or-mainnet)
  - [Scripts](#scripts)
  - [Estimate gas](#estimate-gas)
    - [Estimate gas cost in USD](#estimate-gas-cost-in-usd)
  - [Verify on etherscan](#verify-on-etherscan)
- [Linting](#linting)
- [Formatting](#formatting)
- [Author](#author)
- [Acknowledgements](#acknowledgments)

# Getting Started

## Requirements

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  - You'll know you did it right if you can run `git --version` and you see a response like `git version x.x.x`
- [NodeJS](https://nodejs.org/en/)
  - You'll know you've installed NodeJS right if you can run:
    - `node --version` and get an output like: `vx.x.x`
- [NPM](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) instead of `Yarn`
  - You'll know you've installed npm right if you can run:
    - `npm --version` and get an output like: `x.x.x`

## Quickstart

```bash
git clone https://github.com/dalvinderjitsingh/hardhat-fund-me-fcc
cd hardhat-fund-me-fcc
npm install
```

# Usage

Deploy:

```bash
npx hardhat deploy
```

## Testing

```bash
npx hardhat test
```

### Test Coverage

```bash
npx hardhat coverage
```

# Deployment to a testnet or mainnet

1. Setup environment variables

You'll want to set your `GOERLI_RPC_URL` and `PRIVATE_KEY` as environment variables. You can add them to a `.env` file, similar to what you see in `.env.example`.

- `PRIVATE_KEY`: The private key of your account (like from [metamask](https://metamask.io/)). **NOTE:** FOR DEVELOPMENT, PLEASE USE A KEY THAT DOESN'T HAVE ANY REAL FUNDS ASSOCIATED WITH IT.
  - You can [learn how to export it here](https://metamask.zendesk.com/hc/en-us/articles/360015289632-How-to-Export-an-Account-Private-Key).
- `GOERLI_RPC_URL`: This is the URL of the goerli testnet node you're working with. You can get setup with one for free from [Alchemy](https://alchemy.com/?a=673c802981)

2. Get testnet ETH

Head over to [faucets.chain.link](https://faucets.chain.link/) and get some testnet ETH. You should see the ETH show up in your Metamask.

3. Deploy

```
npx hardhat deploy --network goerli
```

## Scripts

After deploying to a testnet or local net, you can run the scripts.

```bash
npx hardhat run scripts/fund.js
```

or

```bash
npx hardhat run scripts/withdraw.js
```

## Estimate gas

You can estimate how much gas things cost by running:

```bash
npx hardhat test
```

And you'll see an output file called `gas-report.txt`

### Estimate gas cost in USD

To get a USD estimation of gas cost, you'll need a `COINMARKETCAP_API_KEY` environment variable. You can get one for free from [CoinMarketCap](https://pro.coinmarketcap.com/signup).

Then, uncomment the line `coinmarketcap: COINMARKETCAP_API_KEY,` in `hardhat.config.js` to get the USD estimation. Just note, every time you run your tests it will use an API call, so it might make sense to have using Coinmarketcap disabled until you need it. You can disable it by just commenting the line back out.

## Verify on etherscan

If you deploy to a testnet or mainnet, you can verify it if you get an [API Key](https://etherscan.io/myapikey) from Etherscan and set it as an environment variable named `ETHERSCAN_API_KEY`. You can pop it into your `.env` file as seen in the `.env.example`.

In its current state, if you have your API key set, it will auto-verify goerli contracts!

However, you can manually verify with:

```bash
npx hardhat verify --constructor-args arguments.js DEPLOYED_CONTRACT_ADDRESS
```

# Linting

To check linting / code formatting:

```bash
npm run lint
```

or, to fix:

```bash
npm run lint:fix
```

# Formatting

```bash
npm run format
```

# Author

- Name - Dalvinderjit Singh
- Website - [dalvinderjitsingh.github.io](https://dalvinderjitsingh.github.io/)
- LinkedIn - [Dalvinderjit Singh](https://www.linkedin.com/in/dalvinderjit-singh-a40b511b7/)
- Twitter - [@dalvinderjit01](https://twitter.com/dalvinderjit01)

# Acknowledgments

I want to thank [Patrick Collins](https://twitter.com/PatrickAlphaC) and [FreeCodeCamp](https://www.freecodecamp.org) for creating [Web3, Full Stack Solidity, Smart Contract & Blockchain - Beginner to Expert ULTIMATE Course | Javascript Edition](https://github.com/smartcontractkit/full-blockchain-solidity-course-js#lesson-7-hardhat-fund-me).

This course provides a great learning experience and I highly recommend it to anyone wanting to learn Web3 development.
