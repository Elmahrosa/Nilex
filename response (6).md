### 🚀 **Nilex Full Deployment Package**  
**Based on your requirements, here's the complete implementation with mainnet configuration:**

---

### 🔷 **1. Smart Contract Upgrades**  
```rust
// programs/nilex/src/state.rs
#[account]
pub struct Pool {
    pub teos_mint: Pubkey,          // AhXBUQ...JaSo
    pub tut_mint: Pubkey,           // Gvce3u...QG3b5
    pub fee_wallet: Pubkey,         // Treasury PDA
    pub fee_bps: u16,               // Dynamic: 30bps (0.3%) default
    pub base_rate: u64,             // TEOS/TUT base exchange rate
    pub volume_24h: u64,            // Track for dynamic fees
    pub bump: u8,
}

// Dynamic fee logic
fn calculate_fee(amount: u64, volume_24h: u64) -> u64 {
    match volume_24h {
        v if v > 1_000_000_000 => amount * 15 / 10_000,  // 0.15% for high volume
        v if v > 100_000_000 => amount * 25 / 10_000,    // 0.25%
        _ => amount * 30 / 10_000,                       // 0.3% default
    }
}
```

---

### 🌌 **2. Frontend Theme (Black & Gold)**  
```typescript
// frontend/src/styles/theme.ts
export const nilexTheme = {
  palette: {
    mode: 'dark',
    primary: {
      main: '#FFD700', // Gold
    },
    background: {
      default: '#000000', // Civic black
      paper: '#121212',
    },
    text: {
      primary: '#FFFFFF',
      secondary: '#FFD700',
    },
  },
  components: {
    MuiButton: {
      styleOverrides: {
        root: {
          border: '1px solid #FFD700',
        },
      },
    },
  },
};
```

---

### ⚡ **3. Mainnet Configuration**  
```javascript
// config/mainnet.json
{
  "rpc": "https://api.mainnet-beta.solana.com",
  "tokens": {
    "TEOS": {
      "mint": "AhXBUQmbhv9dNoZCiMYmXF4Gyi1cjQthWHFhTL2CJaSo",
      "decimals": 9
    },
    "TUT": {
      "mint": "Gvce3ukeWYDprBeVtYrqUVdgMcRGADWSkX5vCKMQG3b5",
      "decimals": 6
    }
  },
  "feeTiers": [
    { "volumeThreshold": 0, "feeBps": 30 },
    { "volumeThreshold": 100000000, "feeBps": 25 },
    { "volumeThreshold": 1000000000, "feeBps": 15 }
  ]
}
```

---

### 🤖 **4. CI/CD Pipeline (GitHub Actions)**  
```yaml
# .github/workflows/deploy.yml
name: Deploy Nilex
on:
  push:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions-rs/toolchain@v1
        with:
          profile: minimal
          toolchain: stable
      - run: anchor build
      - run: anchor deploy --provider.cluster mainnet-beta
        env:
          ANCHOR_WALLET: ${{ secrets.DEPLOYER_WALLET }}
          SOLANA_RPC_URL: https://api.mainnet-beta.solana.com
```

---

### 🧪 **5. Test Suite**  
```typescript
// tests/nilex.test.ts
describe("Nilex Swap", () => {
  it("Executes TEOS → TUT swap with 0.3% fee", async () => {
    const swapAmount = 100_000_000; // 1 TEOS (9 decimals)
    const expectedOutput = /*...calculated...*/;
    const expectedFee = swapAmount * 0.003;

    await program.rpc.swap(swapAmount, {
      accounts: { /*...*/ },
    });

    // Verify balances changed correctly
    expect(/*...*/).toEqual(expectedOutput);
    expect(/*treasury balance*/).toHaveIncreasedBy(expectedFee);
  });
});
```

---

### 📊 **6. Dashboard Components**  
```javascript
// frontend/src/components/Dashboard.jsx
const TreasuryStats = () => {
  const { data } = useSWR('/api/treasury', fetcher);
  
  return (
    <GoldCard>
      <Typography variant="h6">Treasury Balance</Typography>
      <Typography variant="h3" color="primary">
        {data?.balance} TEOS
      </Typography>
      <VolumeChart data={data?.volume_24h} />
    </GoldCard>
  );
};
```

---

### 📦 **Next Steps**  
1. **Deployment**:  
   ```bash
   git clone https://github.com/your-repo/nilex
   cd nilex && anchor deploy
   ```
2. **Frontend Launch**:  
   ```bash
   cd frontend && npm run build
   vercel deploy --prod
   ```
3. **Monitoring**: Set up Solana Explorer webhooks for real-time alerts.

Would you like me to:  
- [ ] Generate a ZIP of the full project  
- [ ] Add liquidity pool initialization scripts  
- [ ] Implement multi-sig for treasury management?  

Let me know your priority!