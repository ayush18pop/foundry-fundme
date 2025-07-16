# Foundry FundMe

A decentralized crowdfunding smart contract built with Foundry framework. This project demonstrates how to create a funding contract that accepts ETH donations with minimum USD value requirements using Chainlink price feeds.

## Features

- Accept ETH donations with minimum $5 USD equivalent
- Use Chainlink price feeds for ETH/USD conversion
- Owner-only withdrawal functionality
- Gas-optimized withdrawal function
- Comprehensive test suite
- Multi-network deployment support (Local, Sepolia, zkSync)

## Technology Stack

- **Foundry**: Ethereum development framework
- **Solidity**: Smart contract programming language
- **Chainlink**: Decentralized price feeds

## Smart Contracts

- `FundMe.sol`: Main funding contract
- `PriceConverter.sol`: Library for price conversions using Chainlink
- `MockV3Aggregator.sol`: Mock price feed for testing

## Quick Start

### Prerequisites

- [Foundry](https://getfoundry.sh/)
- [Git](https://git-scm.com/)

### Installation

```bash
git clone https://github.com/ayush18pop/foundry-fundme.git
cd foundry-fundme
make install
```

### Build

```bash
make build
```

### Test

```bash
make test
```

### Deploy

#### Local Deployment

```bash
# Start local blockchain
make anvil

# Deploy to local network (in another terminal)
make deploy
```

#### Sepolia Testnet Deployment

```bash
# Add your private key to .env file
echo "SEPOLIA_PRIVATE_KEY=your_private_key_here" >> .env

# Deploy to Sepolia
make deploy-sepolia
```

### Gas Snapshots

```bash
make snapshot
```

## Project Structure

```
├── src/
│   ├── FundMe.sol              # Main funding contract
│   └── PriceConverter.sol      # Price conversion library
├── script/
│   ├── DeployFundMe.s.sol      # Deployment script
│   ├── HelperConfig.s.sol      # Network configuration
│   └── Interactions.s.sol      # Fund/Withdraw scripts
├── test/
│   ├── FundMeTest.t.sol        # Main test suite
│   └── unit/
│       └── ZkSyncDevOps.t.sol  # zkSync compatibility tests
└── lib/                        # Dependencies
```

## Available Make Commands

- `make build` - Build the contracts
- `make test` - Run all tests
- `make deploy` - Deploy to local network
- `make deploy-sepolia` - Deploy to Sepolia testnet
- `make anvil` - Start local blockchain
- `make snapshot` - Generate gas snapshots
- `make format` - Format code
- `make clean` - Clean build artifacts

## Security

This project includes:

- Reentrancy protection
- Access control (owner-only functions)
- Input validation
- Gas optimization patterns

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Patrick Collins](https://github.com/PatrickAlphaC) for educational content
- [Chainlink](https://chain.link/) for price feed oracles
- [Foundry](https://getfoundry.sh/) for the development framework
