# Quantitative Finance

Production trading systems, systematic backtesting, and DeFi analytics tools. Live on Hyperliquid and Binance perpetual futures markets.

---

## AlgoBotVMC

**Production Algorithmic Trading System** | [GitHub (demo)](https://github.com/Mridlll/AlgoBotVMC-demo)

Production-grade 24/7 algorithmic trading bot for Hyperliquid perpetual futures. Runs 20 concurrent strategies across 4 assets (BTC, ETH, SOL, DOGE) with portfolio-level risk management and automated crash recovery.

??? info "Architecture"

    - 4-step signal detection state machine: anchor wave, trigger wave, MFI confirmation, bar replay
    - WaveTrend Oscillator, Money Flow Index, Heikin Ashi, VWAP with std dev bands, divergence detection
    - Portfolio heat tracking with circuit breaker (NORMAL / RECOVERY / HALTED)
    - Bar replay system using timestamps (not bar indices) to match backtest behavior exactly
    - Auto-restart with exponential backoff + watchdog thread
    - Signal detector state persistence across restarts via SQLite
    - FastAPI dashboard for real-time monitoring

**Performance:**

| Metric | Value |
|--------|-------|
| Active strategies | 20 across 4 assets |
| Average Sharpe ratio | 2.01 |
| Projected annual return | $575K |
| Uptime architecture | 24/7 with auto-recovery |

**Stack:** Python 3.11+, asyncio, FastAPI, SQLite, hyperliquid-python-sdk, Discord webhooks

---

## WickTrader

**Quantitative Wick-Based Trading System** | [GitHub](https://github.com/Mridlll/-WickTrader)

Systematic wick-reversal strategy for SOL/USDT perpetual futures with a comprehensive 864-variant grid search backtester and heat-based risk management.

??? info "Methodology"

    - Wick ratio-based signal detection (large candle wicks as reversal zones)
    - Heat zone risk management: GREEN / YELLOW / RED / CRITICAL
    - 864-variant grid search across wick thresholds, exit strategies, directions, and risk profiles
    - Multi-exchange support with automatic failover (Binance + Hyperliquid)

**Backtest Results:**

| Config | Win Rate | Return | Max Drawdown | Sharpe |
|--------|----------|--------|--------------|--------|
| Best risk-adjusted (4% wick SHORT, 15% TP) | 80% | +49.5% | 10.6% | 17.48 |
| Best long (5% wick LONG, 10% TP) | 62.5% | +27.7% | — | — |

Key insight: only 14.4% of 864 tested configurations are profitable — strategy selection is everything.

**Stack:** Python, Binance Futures API, Hyperliquid API, YAML config, Discord webhooks

---

## Liquidity Analyzer

**Multi-DEX Orderbook Analytics** | [GitHub](https://github.com/Mridlll/LiquidityAnalyzer)

Self-hosted tool for real-time orderbook depth analysis and slippage estimation across 5 perpetual DEXes: Hyperliquid, Paradex, Extended, Lighter, and Aster.

**Capabilities:**

- Orderbook depth analysis at price levels from 0.1% to 5%
- Slippage estimation for order sizes $10K to $1M
- Bid/ask imbalance detection
- Cross-DEX best execution venue comparison
- Continuous monitoring with Discord alerts for high slippage, liquidity drops, and wide spreads

No API keys required. Fully local and privacy-focused.

**Stack:** Python, aiohttp (async HTTP), table/JSON/CSV output

---

## Hyperliquid HIP-3 Analytics

**Equity Perpetuals Market Tracker** | [GitHub](https://github.com/Mridlll/Hyperliquid-HIP3)

Community analytics for Hyperliquid HIP-3 equity perpetual markets (trade.xyz). Tracks personal trading volume, market share ranking (Top 1%/5%/10%), and asset-by-asset breakdown across all listed equity perpetuals (TSLA, NVDA, XYZ100, etc.).

**Stack:** Python, Hyperliquid public API

---

## Arkitekt DEX

**Full-Stack DeFi Exchange Frontend** | [GitHub (demo)](https://github.com/Mridlll/Arkitekt-DEX-demo)

Complete decentralized exchange UI with token swapping, liquidity pool management, and staking. Built on the T3 stack.

**Features:** Swap interface, pool management, liquidity provision, staking dashboard, wallet connection (WalletConnect + injected providers), token search with custom token lists.

**Stack:** Next.js 13, TypeScript, Prisma (MySQL), tRPC, Tailwind CSS, wagmi, ethers.js, viem, Redux Toolkit, NextAuth.js

