# 🌊 Nilex – Egypt’s Civic DEX

![GitHub Repo Stars](https://img.shields.io/github/stars/Elmahrosa/Nilex?style=social)
![GitHub Forks](https://img.shields.io/github/forks/Elmahrosa/Nilex?style=social)
![GitHub Last Commit](https://img.shields.io/github/last-commit/Elmahrosa/Nilex)
![GitHub License](https://img.shields.io/github/license/Elmahrosa/Nilex)

**Nilex**, maintained by **Elmahrosa International**, is Egypt's first civic decentralized exchange (DEX) built on the **Solana blockchain**. It empowers transparent, secure, and locally-driven token swaps—starting with native civic assets like **TEOS** and **TUT**, and expanding to stablecoins such as **USDC** and **USDT**.

Unlike conventional DEXs, Nilex operates independently—free from external platforms like Orca or Dexlab. It's designed for Egypt's contributors, creators, and communities, with full control over liquidity, governance, and civic incentives. This project is open-source and actively maintained on GitHub.

---

## 🔁 Supported Swaps
- `TEOS ↔ USDC`
- `TUT ↔ USDT`
- *(Expandable to BONK, USD1, ERT, and other SPL tokens)*

---

## 🧠 About the Movement
Nilex isn't just a product—it's a protocol. Built by Elmahrosa. Powered by contributors. Open to the world. Swap TEOS ↔ TUT directly. No Orca. No Dexlab. Just sovereignty. Join the civic pool. Activate your liquidity. Be part of Egypt's digital backbone.

## 🌐 Live Site
Visit [nilex.teosegypt.com](https://nilex.teosegypt.com) to swap TEOS and TUT with stablecoins directly from your wallet.

---

## 🛠️ Tech Stack
- **Solana Web3.js** + **Anchor** – Smart contract logic
- **Vite** or **Next.js** – Frontend interface
- **Supabase** *(optional)* – Logging, analytics, and contributor tracking

---

## 🪙 Token Addresses
| Token | Address |
|-------|---------|
| TEOS | `AhXBUQmbhv9dNoZCiMYmXF4Gyi1cjQthWHFhTL2CJaSo` |
| TUT | `Gvce3ukeWYDprBeVtYrqUVdgMcRGADWSkX5vCKMQG3b5` |
| USDC | `EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v` |
| USDT | `Es9vMFrzaCERmJfrF4H2FYD4KCoNkY11McCe8BenwNYB` |

---

## 🔐 Treasury Wallet – Civic Liquidity Engine
The Nilex treasury wallet is the backbone of civic liquidity. It receives protocol fees, manages campaign funds, and redistributes assets to contributors and governance pools.

### 📦 Wallet Address
`F1YLmukcxAyZj6zVpi2XaVctmYnuZQB5uHpd3uUpXxr6`

### 🧠 Treasury Logic
- **Fee Collection**: Every swap on Nilex deducts a small civic fee (e.g. 0.5%) routed to the treasury.
- **Liquidity Management**: Treasury funds are used to seed TEOS/TUT pools and defend against whale centralization.
- **Campaign Funding**: Contributors receive TEOS or TUT from the treasury for staking, governance, or referral campaigns.
- **Transparency**: All treasury movements are logged and visible on-chain.

### 🔄 Example Flow
1. User swaps TEOS → USDC
2. 0.5% civic fee sent to treasury
3. Treasury uses USDC to reinforce TEOS pool
4. Contributor earns TEOS from treasury for campaign participation

### 🛡️ Sovereignty Rules
- Treasury cannot be accessed by private wallets
- All disbursements are governed by smart contract logic
- Emergency withdrawals require multi-sig approval

---

## 📦 Installation
Clone the repository and install dependencies:
```bash
git clone https://github.com/Elmahrosa/nilex.git
cd nilex
npm install

---
## 🧱 Repo Structure Blueprint

```plaintext
nilex/
├── smart-contract/       # Anchor-based swap logic (TEOS ↔ TUT)
│   └── src/
│       └── lib.rs        # Core swap logic
│   └── Cargo.toml        # Anchor config
│   └── tests/            # Unit tests
│
├── frontend/             # Vite or Next.js UI
│   └── pages/
│   └── components/
│   └── hooks/
│   └── public/
│   └── styles/
│   └── vite.config.js or next.config.js
│
├── config/
│   └── tokens.js         # TEOS, TUT, decimals, mint addresses
│   └── poolConfig.js     # Swap rates, fees, whitelist logic
│
├── utils/
│   └── walletConnect.js  # Phantom/Backpack integration
│   └── rateLogic.js      # Dynamic swap rate engine
│
├── .env.example          # RPC endpoint, token config
├── README.md             # Mythic launch doc
├── LICENSE               # MIT or custom civic license
```

---

## 🚀 Features

- Custom swap rates and fee logic  
- Treasury wallet integration  
- Whitelist-only access *(optional)*  
- Dashboard for volume and earnings  
- Expandable to support ERT or any SPL token  
- Contributor-first design with civic incentives

---

## 👥 Contributors

- **Ayman** – Founder, architect, and visionary  
- *[Your Devs or Designers]* – Smart contract logic, frontend UI, campaign design  
- *[Community Members]* – Civic liquidity, testing, and governance feedback

Want to contribute? Fork the repo, submit a PR, or join the civic pool.
---
## 📣 Contact & Contributions
For campaign inquiries, AMA sessions, or contributor onboarding:  
📨 [Telegram](https://t.me/Elmahrosapi)  
🌍 [Tally Form](https://tally.so/r/mDL7Yb)

Pull requests and community forks are welcome.

**Nilex is not a product. It’s a protocol.**  
Built by Elmahrosa. Powered by contributors. Open to the world.  
Swap TEOS ↔ TUT. Defend sovereignty. Activate civic liquidity.
