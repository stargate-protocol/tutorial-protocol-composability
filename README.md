# Tutorial Protocol Composability

This tutorial demonstrates how to leverage protocol composability with `Stargate Finance`. You'll learn how to build a smart contract that bridges assets across different chains and then interacts with other DeFi protocols - specifically depositing the bridged assets into `Aave`.

The example contract showcases cross-chain composability by:
1. Transfering `ETH` tokens from `Optimism Sepolia` to `Ethereum Sepolia` using `Stargate`
2. Automatically depositing the received tokens into `Aave` on the destination chain

This pattern can be adapted for various cross-chain use cases and integrated with other DeFi protocols.

## Getting Started

The `/src` directory contains the following smart contracts:

- `StargateComposer.sol`: Main contract that handles composablecross-chain token transfer via Stargate 
- `Receivel.sol`: Contract for receiving callbacks from Stargate bridge operations within `lzCompose` function    

### Prerequisites

- [Node.js](https://nodejs.org/en/download)
- [Forge](https://book.getfoundry.sh/getting-started/installation)
- Funded wallet with ETH on OP Sepolia

### Faucets

- [Optimism Sepolia Faucet](https://www.alchemy.com/faucets/optimism-sepolia)
- [Ethereum Sepolia Faucet](https://www.alchemy.com/faucets/ethereum-sepolia)

### Installation

```shell
yarn install & forge build
```

### Environment Variables

```shell
DEPLOYER_KEY=0x617ef742bb899d8afff3f02c2a80d29e9f60f284636b6c21aa4a436696ebbd86
PRIVATE_KEY=617ef742bb899d8afff3f02c2a80d29e9f60f284636b6c21aa4a436696ebbd86
OPT_CHAIN=optimism-sepolia
OPT_RPC_URL=https://optimism-sepolia.infura.io/v3/fc24592dbb02417f8002dca23a62367b
OPT_ETHERSCAN_API_KEY=92466666666666666666666666666666

SEPOLIA_CHAIN=sepolia
SEPOLIA_RPC_URL=https://sepolia.infura.io/v3/fc24592dbb02417f8002dca23a62367b
SEPOLIA_ETHERSCAN_API_KEY=92466666666666666666666666666666
VERIFIER=etherscan
ETHERSCAN_API_KEY=92466666666666666666666666666666
```

### Usage

Deploy `Receiver` contract on `Ethereum Sepolia`

```shell
make dr
```

Deploy `StargateComposer` contract on `Optimism Sepolia`

```shell
make dc
```

Execute cross-chain transfer of `ETH` from `Optimism Sepolia` to `Ethereum Sepolia`

```shell
make et
```




