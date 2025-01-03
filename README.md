# Lethe Protocol

<div align="center">
    <img src="![image](https://github.com/user-attachments/assets/21abbf72-9399-4396-89a2-2d7a2854d67b)
" />
    <p>
        <a href="https://lethe.pro">Website</a> |
        <a href="https://x.com/LetheProtocol">Twitter</a> |
        <a href="#documentation">Documentation</a>
    </p>
</div>

## Overview

Lethe is a Layer 2 privacy protocol that transforms Solana transactions through multiple protection layers, making them increasingly untraceable while maintaining institutional-grade security and high performance.

### Key Features
- **🛡️ Institutional Privacy**: Complete transaction privacy with institutional-grade security
- **⚡ High Performance**: Lightning-fast transactions leveraging Solana's speed
- **🔒 Quantum Resistant**: Future-proof security through lattice-based cryptography
- **🌊 Flexible Privacy**: Customizable privacy levels from shallow to abyssal depths

## Quick Start

### Installation
```bash
npm install @lethe/sdk
# or
yarn add @lethe/sdk
```

### Basic Usage
```typescript
import { Lethe } from '@lethe/sdk';

// Initialize Lethe
const lethe = new Lethe({
    network: 'mainnet',
    depth: 'deep'
});

// Connect wallet
await lethe.connect(wallet);

// Create private transfer
const transfer = await lethe.createTransaction({
    type: 'transfer',
    params: {
        to: recipient,
        token: 'SOL',
        amount: 100
    }
});

// Send through River Protocol
await lethe.river.send(transfer);
```

## Development

### Prerequisites
- Rust 1.65+
- Solana 1.16+
- Node.js 16+ (for SDK)

### Building
```bash
# Clone repository
git clone https://github.com/lethe-privacy/lethe
cd lethe

# Build
cargo build

# Test
cargo test
```

## Documentation

### Privacy Models
Choose your privacy level:
- **Shallow**: Basic transaction privacy
- **Medium**: Enhanced obfuscation
- **Deep**: Full transaction privacy
- **Abyssal**: Maximum privacy with extended mixins

### Transaction Types
- Private transfers
- Token swaps
- Privacy bundles
- Shielded staking
- Private NFT operations

### Advanced Examples

```typescript
// Create a privacy bundle
const bundle = await lethe.createBundle();

// Add multiple private actions
bundle.add({
    type: 'swap',
    params: { 
        fromToken: 'SOL', 
        toToken: 'USDC', 
        amount: 50 
    }
});

bundle.add({
    type: 'transfer',
    params: { 
        to: recipient, 
        token: 'USDC', 
        amount: 25 
    }
});

// Execute with shared privacy
await lethe.river.send(bundle);
```

## Project Structure

```
lethe/
├── crates/
│   ├── lethe/               # Core protocol
│   ├── lethe-types/         # Common types
│   ├── lethe-computation/   # Computation engine
│   ├── lethe-derive/        # Derive macros
│   └── lethe-utils/         # Utilities
```

## Links

- **Website**: [https://lethe.pro](https://lethe.pro)
- **Twitter**: [@LetheProtocol](https://x.com/LetheProtocol)
- **Documentation**: [docs.lethe.pro](https://lethe.pro/)

## Security

Found a security issue? Please email [security@lethe.io](mailto:security@lethe.io).

## License

MIT License - see [LICENSE](LICENSE) for details.
