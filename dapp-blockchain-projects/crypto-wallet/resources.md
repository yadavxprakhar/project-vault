# Resources for Crypto Wallet

## 📺 Video Tutorials
- **[Build a Crypto Wallet with ethers.js v6 & React (2026)](https://www.youtube.com/watch?v=2KZr6RjXe0E)** - Complete modern wallet build
- **[Blockchain Wallet Development & Security Best Practices](https://www.youtube.com/watch?v=f3J_6cVfHBk)** - Security, MPC, and Account Abstraction
- **[React Native Crypto Wallet with Expo & viem (2026)](https://www.youtube.com/watch?v=1SgLPqHl8hc)** - Mobile wallet tutorial with latest libraries

## 📚 Written Tutorials
- **[Building a Crypto Wallet with ethers.js v6](https://blog.logrocket.com/how-to-build-ethereum-dapp/)** - LogRocket guide (updated for v6)
- **[Key Management & Security Best Practices 2026](https://www.ledger.com/blog/ethereum-security)** - Security guide including MPC and passkeys
- **[BIP39 & Hierarchical Deterministic Wallets](https://github.com/trezor/python-mnemonic)** - Seed phrase and HD wallet standards

## 🔧 Tools & Libraries
- **[ethers.js v6](https://docs.ethers.org/v6/)** - Ethereum library - **RECOMMENDED**
- **[viem](https://viem.sh/)** - Lightweight, type-safe Ethereum library (very popular in 2026)
- **[wagmi](https://wagmi.sh/)** - React hooks for Ethereum
- **[bip39](https://github.com/trezor/python-mnemonic)** - Seed phrase generation
- **[@safe-global/protocol-kit](https://github.com/safe-global/safe-core-sdk)** - Smart wallet integration
- **[crypto-js](https://cryptojs.gitbook.io/)** - Encryption library
- **[Ledger Live](https://www.ledger.com/ledger-live)** - Hardware wallet reference

## 💻 GitHub Repositories
- **[Trust Wallet](https://github.com/trustwallet/wallet-core)** - Production wallet (study reference)
- **[MetaMask](https://github.com/MetaMask/metamask-extension)** - Browser wallet reference
- **[Rainbow Wallet](https://github.com/rainbow-me/rainbow)** - Modern mobile wallet
- **[Safe (formerly Gnosis Safe)](https://github.com/safe-global/safe-contracts)** - Smart wallet reference
- **[ethers.js Wallet Examples](https://github.com/ethers-io/ethers.js/tree/main/packages/wallet)** - Simple wallet examples

## 📖 Learning Resources
- **[BIP32 / BIP39 / BIP44 Standards](https://github.com/trezor/python-mnemonic)** - Key derivation standards
- **[Hierarchical Deterministic Wallets](https://en.wikipedia.org/wiki/Hierarchical_deterministic_wallet)** - Technical overview
- **[Ethereum Accounts & Key Management](https://ethereum.org/en/developers/docs/accounts/)** - Official guide
- **[Account Abstraction (ERC-4337)](https://www.erc4337.io/)** - Modern smart wallet architecture

## 🚀 Sample Wallet Implementation
```typescript
import { ethers } from 'ethers';
import { generateMnemonic, mnemonicToSeedSync } from 'bip39';

export class CryptoWallet {
  private provider: ethers.JsonRpcProvider;
  private wallet: ethers.Wallet;

  constructor(privateKey: string, rpcUrl: string) {
    this.provider = new ethers.JsonRpcProvider(rpcUrl);
    this.wallet = new ethers.Wallet(privateKey, this.provider);
  }

  // Create new wallet with seed phrase
  static createNew() {
    const mnemonic = generateMnemonic();
    const wallet = ethers.Wallet.fromPhrase(mnemonic);
    return {
      address: wallet.address,
      privateKey: wallet.privateKey,
      mnemonic,
      publicKey: wallet.publicKey
    };
  }

  // Get balance
  async getBalance() {
    const balance = await this.provider.getBalance(this.wallet.address);
    return ethers.formatEther(balance);
  }

  // Send transaction
  async sendTransaction(to: string, amount: string) {
    const tx = await this.wallet.sendTransaction({
      to,
      value: ethers.parseEther(amount)
    });
    return tx.wait();
  }

  // Sign message
  async signMessage(message: string) {
    return this.wallet.signMessage(message);
  }
}