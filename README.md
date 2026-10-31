<p align="center">
  <a href="https://github.com/stellar-gaming-hub" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Stellar Gaming Hub Logo" /></a>
</p>

# Stellar Gaming Hub: Frontend API & Client Portal

### IMPORTANT: Never expose private key configurations in production client environments. Always route web3 RPC calls through secure proxies.

A modern, responsive Next.js and TypeScript Web3 frontend platform for discovering games, managing digital assets, and supporting gaming creators through continuous funding streams.

![![License: MIT](https://img.shields.io/badge/license-MIT-yellow.svg)](LICENSE)
![![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/stellar-gaming-hub/Gaming-frontend)
![![Drips Protocol](https://img.shields.io/badge/Funding-Drips_Protocol-blue)](https://drips.network)
![![Node Version](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen)](https://nodejs.org/)

---

## Description

**Stellar Gaming Hub Frontend** provides an open-source gateway for players to explore web3 titles, track achievement badges, interact with on-chain leaderboards, and stream ERC-20 token rewards directly to game repositories.

---

## Game Session & Status API

### New Feature: Secure Session State Retrieval & Drips Stream Tracking

Stellar Gaming Hub now includes a secure, documented state retrieval endpoint with stable session tracking for multi-chain game instances.

**Endpoint:** `GET /api/v1/session/:id/status`

#### Key Features:
* **Stable States:** Versioned session states (`INITIALIZED`, `AUTHENTICATED`, `IN_GAME`, `STREAMING_ACTIVE`, `COMPLETED`, `FAILED`, `CANCELLED`).
* **Chain References:** Detailed chain information including EVM RPC responses, transaction hashes, block numbers, and confirmation timestamps.
* **Security:** Protected by API authentication via `WalletSignatureGuard` with client rate limiting.
* **Query Options:** Configurable responses with `includeDripsDetails` and `includeAssetMetadata` parameters.
* **Error Handling:** Graceful degradation for missing chain network information.

#### Example Usage:

```bash
curl -H "Authorization: Bearer YOUR_WALLET_TOKEN" \
  "http://localhost:3000/api/v1/session/sess_123/status?includeDripsDetails=true"
