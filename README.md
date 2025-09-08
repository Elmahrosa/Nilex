# nilex
Repository created autonomously  by Elmahrosa International 
# 🪙 TEOS Swap Engine
A custom Solana-based swap engine for TEOS and TUT, built to enable direct token exchange without relying on external platforms like Orca or Dexlab.

## 🚀 Features

- Swap TEOS ↔ TUT directly from your wallet
- Custom swap rates and fee logic
- Treasury wallet integration
- Whitelist-only access (optional)
- Dashboard for tracking volume and earnings
- Expandable to support ERT or any SPL token

## 🛠️ Tech Stack

- Solana Web3.js + Anchor (smart contract)
- Vite or Next.js (frontend)
- Supabase (optional backend for logging)

## 📦 Installation

```bash
git clone https://github.com/Elmahrosa/teos-swap-engine.git
cd teos-swap-engine
npm install
teos-swap-engine/
├── smart-contract/         # Anchor-based swap logic (TEOS ↔ TUT)
├── frontend/               # Vite or Next.js UI for swapping
├── config/tokens.js        # Token addresses and decimals
├── utils/                  # Wallet connect, rate logic
├── .env.example            # RPC + token config
├── README.md               # Full documentation
└── LICENSE

