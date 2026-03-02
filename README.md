# PRAXIS - The Blockchain AI Agent

The first AI agent that does everything on Base — deploy contracts, trade tokens, send crypto, analyze data, and build entire dApps. Just ask.

## 🚀 Features

### 1. **AI-Powered Agent** 🤖
- Natural language blockchain interactions
- Execute any onchain action with plain English commands
- Powered by Claude AI + Base network
- Context-aware multi-step task execution

### 2. **Smart Contract Deployment** 📜
- Describe your contract, Praxis writes and deploys it
- Automatic security audit before deployment
- Supports ERC-20, ERC-721, ERC-1155, and custom contracts
- One-click verification on Basescan

### 3. **Autonomous Trading** 📈
- Trade tokens automatically on Base DEXes
- DCA, limit orders, and custom strategies
- Real-time market analysis and routing
- Slippage protection and gas optimization

### 4. **Send & Receive Crypto** 💸
- Transfer any asset on Base with a single command
- Batch transactions for efficiency
- ENS and Basename resolution
- Transaction tracking and notifications

### 5. **Blockchain Analytics** 🔍
- Query any wallet, token, or contract on Base
- Plain language explanations of onchain data
- Portfolio tracking and P&L analysis
- Whale wallet monitoring

### 6. **Full dApp Deployment** 🚀
- From idea to deployed app in minutes
- Praxis writes frontend, backend, and contracts
- Automatic hosting and IPFS deployment
- Built-in testing before launch

### 7. **Built-in Coinbase Wallet** 👛
- Native Coinbase Wallet SDK integration
- No external wallet setup needed
- Create and manage your Base wallet inside Praxis
- Seamless onboarding for crypto beginners
- Always connected to Base network by default

## 📋 Project Structure

```
/praxis
├── contracts/
│   ├── PraxisAgent.sol            # Core AI agent contract
│   ├── PraxisToken.sol            # PRAX governance token
│   └── PraxisTreasury.sol         # Protocol treasury
├── frontend/
│   ├── app/
│   │   ├── page.tsx               # Main chat interface
│   │   ├── dashboard/             # Analytics dashboard
│   │   └── portfolio/             # Portfolio tracker
│   ├── components/
│   │   ├── ChatInterface.tsx      # AI chat UI
│   │   ├── WalletConnect.tsx      # Wallet connection
│   │   ├── TransactionModal.tsx   # Transaction approval
│   │   └── AnalyticsPanel.tsx     # Onchain analytics
│   └── lib/
│       ├── praxis.ts              # Praxis SDK
│       └── base.ts                # Base network utils
├── backend/
│   ├── api/
│   │   ├── chat.ts                # AI chat endpoint
│   │   ├── execute.ts             # Transaction executor
│   │   └── analyze.ts             # Blockchain analyzer
│   └── agents/
│       ├── trader.ts              # Trading agent
│       ├── deployer.ts            # Contract deployer
│       └── analyzer.ts            # Data analyzer
├── mobile/
│   ├── App.tsx                    # React Native app
│   └── screens/                   # Mobile screens
├── scripts/
│   ├── deploy.js                  # Deployment scripts
│   └── verify.js                  # Contract verification
├── tests/
│   ├── contracts/                 # Smart contract tests
│   └── api/                       # API endpoint tests
├── docs/
│   ├── architecture.md            # System architecture
│   ├── api-reference.md           # API documentation
│   └── CONTRIBUTING.md            # Contribution guide
├── abi/
│   ├── PraxisAgent.json           # Agent contract ABI
│   └── PraxisToken.json           # Token contract ABI
├── subgraph/
│   ├── schema.graphql             # Data schema
│   └── subgraph.yaml              # Subgraph config
├── config/
│   ├── .env.example               # Environment template
│   └── chains.ts                  # Network configs
├── deployments/
│   ├── mainnet.json               # Base mainnet addresses
│   └── testnet.json               # Base Sepolia addresses
├── assets/
│   └── logo.svg                   # Praxis logo
├── marketing/
│   └── brand-kit/                 # Brand guidelines
├── governance/
│   └── proposals/                 # DAO proposals
├── .gitignore
├── package.json
├── hardhat.config.js
├── tailwind.config.js
└── tsconfig.json
```

## 🛠️ Setup & Installation

### Prerequisites
- Node.js 18+
- Coinbase Wallet or MetaMask
- Base network configured

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/bankrdex/Praxis.git
cd Praxis
```

2. **Install dependencies:**
```bash
npm install
```

3. **Configure environment variables:**
```bash
cp config/.env.example .env.local

# Edit .env.local with your values:
ANTHROPIC_API_KEY=...              # Claude AI API key
NEXT_PUBLIC_BASE_RPC=...           # Base chain RPC endpoint
NEXT_PUBLIC_WALLETCONNECT_ID=...   # WalletConnect project ID
NEXT_PUBLIC_COINBASE_APP_NAME=...  # Coinbase Wallet SDK app name
NEXT_PUBLIC_COINBASE_APP_LOGO=...  # Coinbase Wallet SDK app logo URL
DEPLOYER_PRIVATE_KEY=0x...         # Contract deployer key
BASESCAN_API_KEY=...               # For contract verification
```

4. **Start development server:**
```bash
npm run dev
```

5. **Open in browser:**
```
http://localhost:3000
```

## 🔐 Security & Best Practices

### AI Agent Security
- **Human-in-the-loop**: Every action requires user approval before execution
- **Sandboxed execution**: AI cannot access keys directly
- **Rate limiting**: Prevents abuse and runaway agents
- **Audit logs**: Every action is logged onchain

### Web3 Security
- Never expose private keys in frontend code
- All transactions shown to user before signing
- Gas estimation before every transaction
- Slippage protection on all swaps
- Stop loss enforcement on trading strategies

### Smart Contracts
- Audited by independent security firms
- Multi-sig treasury management
- Timelocked upgrades (48hr delay)
- Emergency pause functionality

## 📡 API Reference

### POST `/api/chat`
Send a natural language command to Praxis.

**Request:**
```json
{
  "message": "Deploy an ERC-20 token called PraxisCoin with 1M supply",
  "walletAddress": "0x...",
  "sessionId": "abc123"
}
```

**Response:**
```json
{
  "success": true,
  "response": "I'll deploy your ERC-20 token. Please review and approve.",
  "action": "DEPLOY_CONTRACT",
  "preview": {
    "contractType": "ERC-20",
    "name": "PraxisCoin",
    "symbol": "PRXC",
    "supply": "1000000",
    "estimatedGas": "0.002 ETH"
  }
}
```

### POST `/api/execute`
Execute an approved transaction.

**Request:**
```json
{
  "actionId": "xyz789",
  "signature": "0x...",
  "walletAddress": "0x..."
}
```

**Response:**
```json
{
  "success": true,
  "transactionHash": "0x...",
  "explorerUrl": "https://basescan.org/tx/0x...",
  "status": "confirmed"
}
```

## 🔗 Blockchain Networks

| Chain | Use Case | Status |
|-------|----------|--------|
| **Base Mainnet** | Primary network | ✅ Live |
| **Base Sepolia** | Testing & development | ✅ Live |
| **Ethereum** | Cross-chain bridges | 🔜 Coming Soon |
| **Optimism** | Multi-chain expansion | 🔜 Coming Soon |

## 💰 Pricing

| Action | Cost |
|--------|------|
| AI Chat (basic) | Free |
| Contract Deployment | Gas only |
| Token Swap | 0.1% fee |
| Perpetual Trade | 0.05% fee |
| dApp Deployment | 0.01 ETH |
| Analytics Query | Free |

## 📊 Example Commands

### Deploy a Token
```
"Create an ERC-20 token called MyToken with 10 million supply"
→ Praxis writes, audits, and deploys in 30 seconds
```

### Trade Tokens
```
"Buy $500 worth of ETH every Monday using USDC"
→ Praxis sets up automated DCA strategy on Base DEXes
```

### Analyze a Wallet
```
"What is 0x742d35... holding and what is their PnL?"
→ Praxis fetches and explains all onchain data in plain English
```

### Deploy a dApp
```
"Build me an NFT minting website for my collection"
→ Praxis creates smart contract + frontend + deploys everything
```

### Send Crypto
```
"Send 0.1 ETH to presdency.base.eth"
→ Praxis resolves the Basename, estimates gas, and executes
```

## 🗺️ Roadmap

### Phase 1 — Foundation ✅
- [x] Project structure and documentation
- [x] Core AI agent architecture design
- [x] Website and branding

### Phase 2 — MVP 🔨 (In Progress)
- [ ] AI chat interface
- [ ] Wallet connection (Base)
- [ ] Basic token swaps
- [ ] Contract deployment

### Phase 3 — Full Launch 🚀
- [ ] Autonomous trading strategies
- [ ] Full dApp deployment
- [ ] Mobile app (iOS & Android)
- [ ] PRAX governance token

### Phase 4 — Expansion 🌍
- [ ] Multi-chain support
- [ ] Developer API & SDK
- [ ] Praxis marketplace
- [ ] DAO governance

## 🤝 Contributing

We welcome builders from West Africa and the global Base ecosystem!

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'Add my feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

See [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md) for full guidelines.

## 📚 Documentation

- [Architecture Overview](docs/architecture.md)
- [API Reference](docs/api-reference.md)
- [Smart Contract Docs](contracts/README.md)
- [Contributing Guide](docs/CONTRIBUTING.md)

## 🚨 Disclaimer

**Praxis is currently in active development.**

- Smart contracts are not yet audited for production
- Test thoroughly on Base Sepolia before mainnet use
- Trading and leverage carry significant financial risk
- Always review transactions before approving
- Praxis is not responsible for onchain losses

## 🎯 Community & Support

| Platform | Link |
|---------|------|
| Discord | [@PRESDENCY3](https://discord.com) |
| Farcaster | [@Presdency.eth](https://warpcast.com) |
| GitHub Issues | [Report a bug](https://github.com/bankrdex/Praxis/issues) 

## 📄 License

MIT License — See [LICENSE](LICENSE) for details.

---

**Built with ❤️ by Hamza Muhammad ([@PRESDENCY3](https://discord.com))**

*Bringing the full power of Base blockchain to everyone through AI.*

[![Built on Base](https://img.shields.io/badge/Built%20on-Base-0052FF?style=flat-square)](https://base.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![Status: In Development](https://img.shields.io/badge/Status-In%20Development-orange?style=flat-square)]()
