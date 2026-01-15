# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Structure

This is a multi-project repository containing several distinct applications:

### Web3/Blockchain Projects
- **x402/**: Payment protocol implementation - TypeScript monorepo with Turbo
- **payai/**: Next.js application with Web3 integration (Solana/Ethereum wallets)
- **agentmarket/**: Vite + React application with Web3 functionality
- **my-web3-homepage/**: Next.js 15 personal website with TypeScript

### 3D/Three.js Projects  
- **Bing-Shop/**: Three.js experience with webpack bundling - interactive 3D ramen shop
- **BingZhang/**: Three.js personal portfolio with webpack bundling

### React Applications
- **rick-rubin-experience/**: Create React App with PWA template
- **go-game/**: Vanilla JavaScript Go game implementation
- **payai/**: Next.js with Solana and Ethereum wallet integration

## Common Development Commands

### Three.js Projects (Bing-Shop, BingZhang)
```bash
cd Bing-Shop  # or BingZhang
npm run dev     # Development server with webpack
npm run build   # Production build
npm run deploy  # Deploy to Vercel
```

### Next.js Projects (payai, my-web3-homepage)
```bash
cd payai  # or my-web3-homepage
npm run dev     # Development server
npm run build   # Production build
npm run start   # Production server
npm run lint    # ESLint
```

### Vite Projects (agentmarket)
```bash
cd agentmarket
npm run dev     # Development server
npm run build   # Production build
npm run preview # Preview production build
```

### x402 Protocol (TypeScript Monorepo)
```bash
cd x402/typescript
pnpm install    # Install dependencies
pnpm build      # Build all packages
pnpm test       # Run unit tests
pnpm lint       # Lint all packages
```

### React Projects (rick-rubin-experience)
```bash
cd rick-rubin-experience
npm start       # Development server
npm run build   # Production build
npm test        # Run tests
```

## Architecture Notes

### Three.js Applications Architecture
- **Experience Class**: Singleton pattern managing the entire 3D scene
- **Utils**: Reusable utilities (Debug, Sizes, Time, Resources, EventEmitter)
- **World**: Scene objects and environment management
- **Webpack Configuration**: Separate dev/prod configs with asset optimization

### x402 Protocol Architecture
- **Monorepo Structure**: Uses pnpm workspaces and Turbo for build orchestration
- **Payment Schemes**: Extensible payment protocol with different blockchain schemes
- **Facilitator Pattern**: Third-party servers for payment verification and settlement
- **Express Middleware**: Simple integration for accepting payments in HTTP services

### Web3 Integration Patterns
- **Wallet Adapters**: Standardized wallet connection across Solana and Ethereum
- **Multiple Chain Support**: Projects support both Solana and Ethereum ecosystems
- **Payment Integration**: Several projects integrate x402 payment protocol

## Key Dependencies

### Three.js Stack
- Three.js, GSAP, lil-gui, stats.js, postprocessing, howler

### Web3 Stack  
- Solana: @solana/wallet-adapter-*, @solana/web3.js
- Ethereum: wagmi, viem, ethers, @rainbow-me/rainbowkit
- x402 protocol: x402-express for payment integration

### Build Tools
- Webpack (Three.js projects), Vite (modern React), Next.js (full-stack)
- TypeScript across most projects
- Tailwind CSS for styling

## Environment Setup

Projects requiring environment variables typically need:
- **FACILITATOR_URL**: For x402 payment integration
- **ADDRESS**: Ethereum address for receiving payments
- **Private keys**: For client-side payment examples (development only)

Check individual project .env.example files or README files for specific requirements.