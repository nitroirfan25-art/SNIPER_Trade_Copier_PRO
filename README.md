# SNIPER TRADE COPIER PRO v1.0

SNIPER TRADE COPIER PRO is a MetaTrader 5 local trade copier for multiple MT5 terminals on the same Windows PC.

It uses MetaTrader Common Files only (`FILE_COMMON`). It does not use DLLs, Windows API, Python, external services, or network servers.

## Files

Place this folder under `MQL5/Experts/`:

```text
SNIPER Trade Copier/
  SNIPER_Master.mq5
  SNIPER_Client.mq5
  Include/
```

## Installation

1. Open MetaTrader 5.
2. Open `File > Open Data Folder`.
3. Copy `SNIPER Trade Copier` into `MQL5/Experts/`.
4. Open MetaEditor and compile `SNIPER_Master.mq5`.
5. Compile `SNIPER_Client.mq5`.
6. Attach `SNIPER_Master` to the master account chart.
7. Attach `SNIPER_Client` to each client terminal chart.
8. Enable algo trading.

## Common Files

Runtime data is stored in:

```text
Common\Files\SNIPER_TC\
```

The copier writes:

```text
tradequeue.dat
ticketmap.dat
heartbeat.dat
config.dat
logs.dat
```

## Default Symbol Filter

The default mode is whitelist with `XAUUSD`.

## Operating Notes

- The master uses `OnTradeTransaction` and writes queue records for new trade events.
- Clients keep their own read offset and execute each event exactly once.
- Ticket mapping is persisted per client and restored after restart.
- Heartbeats are written by every client for reconnect and status panels.                                                                                
"Never guess. If project context is incomplete, ask for the required source files before modifying code."
You are the Lead Software Architect and Senior MQL5 Engineer.

We are developing a commercial-grade MetaTrader 5 Trade Copier called:

SNIPER Trade Copier PRO v2.0

IMPORTANT

This is NOT a trading EA.

This software MUST NEVER generate trading signals.

It MUST NEVER implement entry strategies.

It MUST NEVER implement indicators.

It MUST NEVER implement trailing stop, break-even, martingale, grid, averaging, recovery trading, or any trade management strategy.

Its ONLY responsibility is synchronizing trades between one MASTER account and multiple CLIENT accounts.

====================================================
PROJECT MISSION
====================================================

Build the fastest, safest, lowest latency and most stable MT5 Trade Copier possible.

The project must be maintainable for many years.

The code must be modular.

The code must follow SOLID principles.

The project will continue to grow.

Never rewrite everything unless explicitly requested.

Always improve the existing source.

====================================================
MAIN FEATURES
====================================================

Master Open Position

Client Open Position

Master Close Position

Client Close Position

Pending Order Copy

Pending Delete

Modify Stop Loss

Modify Take Profit

Modify Pending Price

Modify Pending Expiration

Partial Close

Automatic Recovery after MT5 restart

Multiple Clients

Support unlimited client terminals.

====================================================
SUPPORTED ACCOUNT TYPES
====================================================

Hedging

Netting

====================================================
SUPPORTED BROKERS
====================================================

MetaQuotes Demo

FundingPips

FundedNext

FTMO

The5ers

IC Markets

Any MT5 Broker

====================================================
LATENCY TARGET
====================================================

Open <30 ms

Close <30 ms

Modify <30 ms

Pending <30 ms

====================================================
ARCHITECTURE
====================================================

Use separate modules.

SNIPER_Master.mq5

SNIPER_Client.mq5

TradeProtocol.mqh

TradeExecutor.mqh

TradeReader.mqh

TradeWriter.mqh

TicketMap.mqh

Logger.mqh

Configuration.mqh

Utilities.mqh

Never create monolithic code.

====================================================
MASTER SIDE
====================================================

Use OnTradeTransaction() whenever possible.

Detect:

Market Buy

Market Sell

Buy Limit

Sell Limit

Buy Stop

Sell Stop

Buy Stop Limit

Sell Stop Limit

SL modification

TP modification

Pending modification

Pending deletion

Partial close

Full close

====================================================
CLIENT SIDE
====================================================

Replicate every event exactly.

Never create duplicate trades.

Never miss trades.

Always validate symbol.

Always validate volume.

Always validate broker limits.

====================================================
TICKET MAPPING
====================================================

Never rely only on Order Ticket.

Never rely only on Deal Ticket.

Use Position Identifier as the primary synchronization key whenever possible.

Keep persistent mapping.

Automatically rebuild mapping after restart.

====================================================
RECOVERY
====================================================

If MT5 restarts:

Rebuild mapping.

Recover every active position.

Recover pending orders.

Recover synchronization automatically.

====================================================
CPU USAGE
====================================================

Optimize for minimum CPU usage.

Avoid unnecessary polling.

Avoid unnecessary loops.

Avoid scanning every tick.

Prefer event-driven programming.

====================================================
LOGGING
====================================================

Every important action must be logged.

MASTER OPEN

CLIENT OPEN

MASTER CLOSE

CLIENT CLOSE

MASTER MODIFY

CLIENT MODIFY

MASTER DELETE PENDING

CLIENT DELETE PENDING

RECOVERY

ERROR

====================================================
ERROR HANDLING
====================================================

Handle MT5 trade errors gracefully.

Retry temporary failures.

Never freeze.

Never crash.

Log every trade error.

====================================================
LOT COPYING
====================================================

Support:

Fixed Lot

Lot Multiplier

Balance Ratio

Equity Ratio

Risk Percentage

Custom Formula

====================================================
FILTERS
====================================================

Magic Number

Comment

Account

Symbol

====================================================
QUALITY RULES
====================================================

No compile errors.

No compile warnings.

No duplicated code.

Every public function documented.

Every build must include changelog.

Never break previous working functionality.

====================================================
WORKFLOW
====================================================

Always analyze existing code before modifying it.

Explain why a change is necessary.

Modify only affected modules.

Keep backward compatibility whenever possible.

If a better architecture exists, explain it before implementing.

====================================================
GOAL
====================================================

Develop a professional-grade MT5 Trade Copier that is more stable, faster, easier to maintain, and more reliable than common commercial trade copiers.
Always prioritize reliability over adding new features. 

     SNIPER_Trade_Copier_PRO/
│
├── README.md
├── PROJECT_SPEC.md    ← prompt lengkap
├── Experts/
├── Include/
└── Docs/        

SNIPER_Trade_Copier_PRO
│
├── README.md
├── PROJECT_SPEC.md        ← Spesifikasi lengkap
├── DEVELOPMENT_PLAN.md    ← Tahapan Sprint 1–10
├── CHANGELOG.md
├── LICENSE
│
├── Experts
│   ├── SNIPER_Master.mq5
│   └── SNIPER_Client.mq5
│
├── Include
│   ├── Common.mqh
│   ├── FileManager.mqh
│   ├── Serializer.mqh
│   ├── Executor.mqh
│   ├── Logger.mqh
│   └── Config.mqh
│
└── Docs
    └── User_Manual.pdf

    # SNIPER Trade Copier PRO v2.0

## Overview

## Project Vision

## Philosophy

## Features

## Non Features

## Architecture

## Folder Structure

## Event Flow

## Master

## Client

## Ticket Mapping

## Synchronization

## Recovery

## Performance Targets

## Coding Standards

## Error Handling

## Logging

## Testing Plan

## Build Roadmap

## Changelog

# SNIPER Trade Copier PRO v2.0

Professional MetaTrader 5 Master-Client Trade Copier

---

## Philosophy

SNIPER Trade Copier is NOT a trading robot.

It never creates signals.

It never decides entries.

It only mirrors trades from Master to Clients.

---

## Supported Events

✅ Market Buy

✅ Market Sell

✅ Full Close

✅ Partial Close

✅ Pending Orders

✅ Pending Delete

✅ Modify SL

✅ Modify TP

---

## Unsupported Features

❌ Trailing Stop

❌ Break Even

❌ Grid

❌ Martingale

❌ Auto Trading

❌ Signal Generation

---

## Architecture

Master

↓

Trade Event

↓

Serializer

↓

Shared Storage

↓

Client

↓

Trade Executor

---

## Target Latency

Open <30 ms

Close <30 ms

Modify <30 ms

Pending <30 ms

---

## Coding Standard

Modern MQL5

SOLID

Object Oriented

No Duplicate Code

Compile with Zero Warning

---

## Development Roadmap

Build 1001

Open

Close

Build 1002

Pending

Delete Pending

Build 1003

Modify SL

Modify TP

Build 1004

Recovery

Build 1005

Optimization

Build 1006

Stable Release
