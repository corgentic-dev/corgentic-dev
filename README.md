<div align="center">
  <img src="https://iili.io/qZsS96v.png" alt="CORGENTIC" width="120" />

  <h1>CORGENTIC</h1>

  <p><strong>AI Agent Economic Operating Layer on Solana</strong></p>

  <p>Deploy autonomous AI agents on-chain. Launch agent tokens. Route fees. Manage treasuries. All from your terminal.</p>

  <br />

  [![npm version](https://img.shields.io/npm/v/corgentic?color=7c3aed&label=corgentic&style=flat-square)](https://www.npmjs.com/package/corgentic)
  [![SDK version](https://img.shields.io/npm/v/@corgentic/sdk?color=7c3aed&label=%40corgentic%2Fsdk&style=flat-square)](https://www.npmjs.com/package/@corgentic/sdk)
  [![License: MIT](https://img.shields.io/badge/License-MIT-7c3aed?style=flat-square)](LICENSE)
  [![Built on Solana](https://img.shields.io/badge/Built%20on-Solana-9945FF?style=flat-square&logo=solana&logoColor=white)](https://solana.com)
  [![Follow on X](https://img.shields.io/badge/Follow-%40corgentic-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/corgentic)

  <br />

  [Live App](https://corgentic.app) · [Docs](https://corgentic.app/docs) · [API Reference](https://corgentic.app/api-reference) · [Marketplace](https://corgentic.app/marketplace) · [X / Twitter](https://x.com/corgentic)

</div>

---

## What is CORGENTIC?

CORGENTIC is an open infrastructure protocol for building, deploying, and monetizing autonomous AI agents on the Solana blockchain. It provides the complete economic stack an agent needs to operate independently — on-chain identity, a native SPL token, a live treasury, programmable fee routing, and a marketplace for agent services.

CORGENTIC is **CLI-first**. Developers deploy agents, launch tokens, and configure fee routes entirely from their terminal. The web dashboard provides real-time monitoring and management for deployed agents.

---

## Features

| Feature | Description |
|---|---|
| **Agent Deployment** | Deploy autonomous AI agents on-chain with a single CLI command |
| **On-Chain Identity** | Every agent gets a unique Solana-linked identity, publicly verifiable and composable |
| **Token Launch** | Launch a native SPL token for your agent — set supply, price, and symbol |
| **Treasury Management** | Per-agent on-chain treasury tracking SOL, USDC, and token balances |
| **Fee Routing** | Programmable fee splits: treasury, protocol, and burn — triggered by transactions, thresholds, or flat rules |
| **Marketplace** | List agent services for other agents and users to discover and subscribe |
| **TypeScript SDK** | Full-featured `@corgentic/sdk` for integrating CORGENTIC into any Node.js app |
| **Secure Dashboard** | Authenticated web dashboard gated behind Privy Solana wallet auth |

---

## Quick Start

### CLI

```bash
# Install globally
npm install -g corgentic

# Authenticate
corgentic login

# Initialize a new agent project
corgentic init my-agent

# Deploy agent on-chain
corgentic deploy
```

### SDK

```bash
npm install @corgentic/sdk
```

```typescript
import { CorgenClient } from "@corgentic/sdk";

const client = new CorgenClient({
  apiKey: process.env.CORGENTIC_API_KEY,
});

// List your agents
const { agents } = await client.agents.list();

// Get agent treasury
const treasury = await client.treasury.get(agentId);

// List marketplace services
const { services } = await client.marketplace.list({ category: "trading" });
```

---

## CLI Reference

```
corgentic login                   Authenticate with your API key
corgentic init [name]             Initialize a new agent project
corgentic deploy                  Deploy agent on-chain from corgentic.json
corgentic agent list              List all your deployed agents
corgentic agent status <id>       Check agent status and stats
corgentic agent stop <id>         Deactivate a running agent
corgentic token launch            Launch an SPL token for your agent
corgentic token status <id>       Get token price, supply, and holders
corgentic treasury balance <id>   View agent treasury balances
corgentic marketplace list        Browse available agent services
corgentic marketplace publish     List your agent service on the marketplace
```

**Environment variables:**

```bash
CORGENTIC_API_KEY=your_api_key
CORGENTIC_BASE_URL=https://corgentic.app/api   # optional, defaults to production
```

---

## SDK Reference

```typescript
// Agents
client.agents.list(params?)
client.agents.get(id)
client.agents.create(data)
client.agents.update(id, data)

// Treasury
client.treasury.get(agentId)
client.treasury.transactions(agentId, params?)

// Tokens
client.tokens.list(params?)
client.tokens.get(id)
client.tokens.launch(data)

// Marketplace
client.marketplace.list(params?)
client.marketplace.get(id)
client.marketplace.publish(data)
client.marketplace.subscribe(serviceId, data)

// Fee Routes
client.feeRoutes.list(params?)
client.feeRoutes.create(data)
```

---

## Architecture

```
┌─────────────────────────────────────────────────────┐
│                   CORGENTIC Stack                   │
├─────────────┬───────────────────────┬───────────────┤
│  CLI        │  Web Dashboard        │  SDK          │
│  corgentic  │  corgentic.app        │  @corgentic/  │
│  (npm)      │  (React + Vite)       │  sdk (npm)    │
├─────────────┴───────────────────────┴───────────────┤
│              REST API  (Express + TypeScript)        │
├─────────────────────────────────────────────────────┤
│         PostgreSQL (Drizzle ORM)                    │
├─────────────────────────────────────────────────────┤
│         Solana Blockchain (Wallet auth via Privy)   │
└─────────────────────────────────────────────────────┘
```

---

## Tech Stack

- **Blockchain:** Solana (SPL tokens, on-chain identity)
- **Auth:** [Privy](https://privy.io) — Solana wallet authentication
- **Backend:** Node.js, Express, TypeScript
- **Database:** PostgreSQL with [Drizzle ORM](https://orm.drizzle.team)
- **Frontend:** React, Vite, TailwindCSS
- **CLI:** Node.js, TypeScript, [`conf`](https://github.com/sindresorhus/conf)
- **Packages:** pnpm workspaces monorepo

---

## Links

| Resource | URL |
|---|---|
| Live App | https://corgentic.app |
| Documentation | https://corgentic.app/docs |
| API Reference | https://corgentic.app/api-reference |
| Marketplace | https://corgentic.app/marketplace |
| Token Launches | https://corgentic.app/launches |
| CLI on npm | https://www.npmjs.com/package/corgentic |
| SDK on npm | https://www.npmjs.com/package/@corgentic/sdk |
| Twitter / X | https://x.com/corgentic |
| GitHub | https://github.com/corgentic-dev |

---

## License

MIT — see [LICENSE](LICENSE) for details.

---

<div align="center">
  <img src="https://iili.io/qZsS96v.png" alt="CORGENTIC" width="48" />
  <br />
  <sub>Built by the CORGENTIC team · <a href="https://x.com/corgentic">@corgentic</a></sub>
</div>
