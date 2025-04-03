# Tutorial Protocol Composability

![Stargate Finance](https://stargate.finance/static/og-image.jpg)

This tutorial demonstrates how to leverage composability with `Stargate Finance` protocol. 
You'll learn how to build a smart contract that bridges assets across different chains and then interacts with other DeFi protocols - specifically depositing the transfered assets into `Aave`.

The example contract showcases cross-chain composability by:

1. Transfering `ETH` tokens from `Optimism Sepolia` to `Ethereum Sepolia` using `Stargate`
2. Automatically depositing the received tokens into `Aave` on the destination chain

This pattern can be adapted for various cross-chain use cases and integrated with other DeFi protocols.

## Getting Started

The `/src` directory contains the following smart contracts:

- `StargateComposer.sol`: Main contract that handles composablecross-chain token transfer via Stargate 
- `Receivel.sol`: Contract for receiving callbacks from Stargate bridge operations within `lzCompose` function    

### Prerequisites

- 🔸 [Node.js](https://nodejs.org/en/download)
- 🔸 [Forge](https://book.getfoundry.sh/getting-started/installation)
- 🔸 Funded wallet with ETH on OP Sepolia

### Faucets

- [Optimism Sepolia Faucet](https://www.alchemy.com/faucets/optimism-sepolia)
- [Ethereum Sepolia Faucet](https://www.alchemy.com/faucets/ethereum-sepolia)

### Installation

```shell
yarn install & forge build
```

### Usage

Deploy `StargateComposer` contract on `Optimism Sepolia`

```shell
make dc
# Update address of the composer in TransferEth.s.sol
```

Deploy `Receiver` contract on `Ethereum Sepolia`

```shell
make dr
```

Execute cross-chain transfer of `ETH` from `Optimism Sepolia` to `Ethereum Sepolia`

```shell
make et
```

## Join the community

Join our community of developers creating universal apps.

- [Stargate on GitHub](https://github.com/stargate-protocol): Stargate protocol open source code.
- [Discord Builders Community](https://discord.com/channels/903022426856755220/1313128694273020027): Chat with Stargate builders community.




