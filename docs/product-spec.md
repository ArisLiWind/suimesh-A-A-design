# A@A — Product Specification v0.1

> Status: Pre-design phase | Last updated: 2026-05-22

---

## 1. Platform Positioning

**A@A (Agent-at-Agent)** is a decentralized, fully automated, 24/7 intelligent trading platform built on the Sui blockchain, powered by the **SuiMesh** communication protocol.

- **Platform name**: A@A
- **Tagline**: Agent at Agent. Trade at Scale.
- **Underlying protocol**: SuiMesh (handles Agent messaging, identity, on-chain context)
- **Core differentiator**: Multi-user Agent cooperation — not just personal automation, but a living Agent ecosystem where users' Agents collaborate, copy-trade, and form consensus.

### Layer Separation

```
┌─────────────────────────────────────┐
│           A@A Application           │  ← Trading UI, Agent Marketplace,
│   (Agent Network, Flow Editor,      │    Flow Editor, Monitor, Audit Log
│    Monitor, Marketplace, Log)       │
├─────────────────────────────────────┤
│         SuiMesh Protocol            │  ← Agent messaging, identity,
│  (A2A communication layer)          │    context ownership, verification
├─────────────────────────────────────┤
│            Sui Blockchain           │  ← Settlement, smart contracts,
│                                     │    on-chain audit trail
└─────────────────────────────────────┘
```

---

## 2. Core Concepts

### 2.1 Agent Node
Every user owns one or more **Agent Nodes** — autonomous, composable trading bots that:
- Pull data from connected source nodes (market feeds, news APIs, AI analyzers)
- Execute strategies via on-chain smart contracts on Sui
- Expose a public performance profile (optional)
- Communicate with other users' Agents via the SuiMesh A2A protocol

### 2.2 Node Types

| Type | Icon | Description |
|------|------|-------------|
| My Trading Agent | ◉ | User's primary agent — executes trades |
| Market Data Node | ◈ | Real-time price feeds (CEX/DEX) |
| News / Sentiment Node | ◈ | RSS, Twitter/X, on-chain signal parsers |
| AI Analysis Node | ◈ | LLM-powered signal interpretation |
| Strategy Agent (Public) | ◉ | Other users' agents available for copy-trading |
| Copy-Trade (Follow) Node | ◆ | One-click follow another agent's decisions |
| Risk Guard Node | ◆ | Automatic drawdown limits, pause conditions |

### 2.3 Node Connections
Connections are directional and typed:
- **Data feed** — source → agent (unidirectional)
- **Copy-trade** — followed agent → your agent (mirrored execution)
- **Collaboration** — peer agents sharing signals (bidirectional)

---

## 3. Core User Scenarios

### Scenario A — "Set and Forget"
> User creates their Trading Agent, connects to Market Data + News Node, sets risk parameters, deploys. Agent runs 24/7 on Sui via SuiMesh.

### Scenario B — "Follow a Pro"
> User discovers a top-performing public agent in the A@A Marketplace. One click: "Follow". Their own Agent mirrors all trades with configurable size multiplier and risk cap.

### Scenario C — "Conditional Copy"
> User follows Agent B, but adds a condition: "If market volatility index > 40 OR breaking news sentiment is negative, pause copy-trading". Risk Guard Node handles this automatically.

### Scenario D — "Build a Network"
> Power user creates a mesh: News Agent → AI Analyzer → My Agent ↔ Agent B (peer strategy sharing) → Copy-traded by 50 followers.

---

## 4. Interface Structure (5 Main Views)

### View 1: Agent Network Canvas
- Central topology view showing all connected Agent nodes
- Each node: live status badge, mini performance sparkline, connection lines
- Drag to connect nodes, click to configure
- Global search + filter nodes by type / performance

### View 2: Agent Marketplace
- Grid of public agents sorted by: ROI / Followers / Sharpe Ratio / Recent Activity
- Agent card: avatar, strategy name, 30d return chart, follower count, tags
- "Follow" button triggers instant copy-trade setup wizard
- My Followed Agents panel (sidebar)

### View 3: Flow Editor
- Drag-and-drop canvas (no-code strategy builder)
- Left panel: node library (Data Sources, Analysis, Actions, Guards)
- Right panel: selected node configuration
- "Test Run" — dry-run strategy against historical data
- Deploy → pushes config to on-chain agent contract via SuiMesh

### View 4: Strategy Monitor
- Asset equity curve (interactive chart)
- Active positions table
- Recent trades feed
- Node health status panel
- Risk metrics: drawdown, position size, daily P&L, volatility index

### View 5: Decision Audit Log
- Timeline of all decisions made by all connected nodes
- Each entry: timestamp, triggering node, signal received, action taken, tx hash
- Click any entry: expand full decision chain trace
- Export to CSV / on-chain attestation via SuiMesh

---

## 5. Key Interaction Principles

1. **Visual first** — Every connection, every decision is visible. No black boxes.
2. **One-click depth** — Complex operations (copy-trade setup, risk config) are one click to start, guided wizards to complete.
3. **Traceable by default** — Every action produces an auditable log entry, anchored on-chain via SuiMesh.
4. **Progressive disclosure** — Simple view for beginners, full canvas for power users.
5. **Risk-first UX** — Risk Guard configuration is prominently surfaced, never buried.

---

## 6. Design System Tokens

| Token | Value |
|-------|-------|
| Background primary | `#0A0E1A` |
| Background surface | `#111827` |
| Background card | `#161D2F` |
| Accent blue | `#3B82F6` |
| Accent cyan | `#06B6D4` |
| Text primary | `#F8FAFC` |
| Text secondary | `#94A3B8` |
| Success | `#22C55E` |
| Danger | `#EF4444` |
| Warning | `#F59E0B` |
| Border | `rgba(255,255,255,0.08)` |
| Node online | `#22C55E` |
| Node offline | `#6B7280` |
| Node alert | `#F59E0B` |

Font: Inter / SF Pro (system) for UI, JetBrains Mono for logs/hashes.
