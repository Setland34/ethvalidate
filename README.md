# EthValidate

This tool is to validate transaction, address, and token balance from public ethereum nodes.

## Usage

(Optional parameters)

### Transaction
- **tx** - transactionhash
- Sample usage: [https://etherscan.github.io/ethvalidate/?tx=0xa2882cca690d1898d7cc13ca9c978c04e83179eb07c0a6aa7f2fba355d50bd52](https://etherscan.github.io/ethvalidate/?tx=0xa2882cca690d1898d7cc13ca9c978c04e83179eb07c0a6aa7f2fba355d50bd52)

### Address
- **a** - address
- Sample usage: [https://etherscan.github.io/ethvalidate/address?a=0x3f5ce5fbfe3e9af3971dd833d26ba9b5c936f0be](https://etherscan.github.io/ethvalidate/address?a=0x3f5ce5fbfe3e9af3971dd833d26ba9b5c936f0be)

### Token
- **a** - address
- **c** - contractaddress
- Sample usage: [https://etherscan.github.io/ethvalidate/token?a=0x3f5ce5fbfe3e9af3971dd833d26ba9b5c936f0be&c=0x12480e24eb5bec1a9d4369cab6a80cad3c0a377a](https://etherscan.github.io/ethvalidate/token?a=0x3f5ce5fbfe3e9af3971dd833d26ba9b5c936f0be&c=0x12480e24eb5bec1a9d4369cab6a80cad3c0a377a)

### Network
- **n** - network
  - Mainnet
  - QuickNode
  - infura
  - mycrypto
  - myetherwallet
  - chainstack
  - Testnet
  - sepolia_infura
  - goerli_infura
- Sample usage: 
  - [https://etherscan.github.io/ethvalidate/?n=infura,mycrypto](https://etherscan.github.io/ethvalidate/?n=infura,mycrypto)
  - [https://etherscan.github.io/ethvalidate/?n=sepolia_infura](https://etherscan.github.io/ethvalidate/?n=sepolia_infura)

## Disclaimer
Please take note that this is a beta version feature and is provided on an "as is" and "as available" basis. Etherscan does not give any warranties and will not be liable for any loss, direct or indirect, through continued provision of this beta feature.

## CI Workflow

We use GitHub Actions for Continuous Integration. The workflow is defined in the `.github/workflows` directory. Below is an example of the CI workflow:

```yaml
name: CI

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '16'

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test
