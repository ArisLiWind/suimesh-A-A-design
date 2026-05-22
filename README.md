# A@A — Design Repository

> Agent-at-Agent Automated Trading Platform, powered by SuiMesh

This repository contains the **pre-launch design phase** of A@A: interaction design, visual specifications, interface prototypes, and node relationship diagrams.

## What is A@A?

**A@A (Agent-at-Agent)** is a decentralized, Agent-first automated trading platform built on Sui. Every user owns a trading Agent node. Agents connect to each other — and to market data, news feeds, and AI analysis nodes — forming a living, collaborative intelligence network.

> **SuiMesh** is the underlying communication layer that A@A runs on. SuiMesh handles the Agent-to-Agent messaging protocol, identity verification, and on-chain context ownership. A@A is the trading application built on top of it.

## Contents

| Path | Description |
|------|-------------|
| `docs/` | Product spec, interaction design, node architecture |
| `prototypes/` | HTML interface prototypes (open in browser) |
| `assets/` | Design assets, illustrations |

## Core Concept

Every user on A@A owns one or more Agent nodes. These Agents can:
- Connect to market data sources, news APIs, and AI analysis nodes
- Follow and copy-trade other users' public Agents with one click
- Collaborate peer-to-peer across users, forming a decentralized strategy network
- Execute trades autonomously, 24/7, with full on-chain auditability

### Key Screens
1. **Agent Network View** — topology canvas, live node status & connections
2. **Agent Marketplace** — discover & subscribe to top-performing Agents
3. **Flow Editor** — drag-and-drop strategy builder, no code required
4. **Strategy Monitor** — real-time P&L, positions, risk dashboard
5. **Decision Audit Log** — full on-chain traceable decision history

## Stack / Protocol

| Layer | Name | Role |
|-------|------|------|
| Communication | **SuiMesh** | Agent messaging, identity, context ownership |
| Application | **A@A** | Trading UI, Agent marketplace, flow editor |
| Chain | **Sui** | Settlement, smart contracts, on-chain audit |

---

*Own the Context. Verify the Action. — SuiMesh*
