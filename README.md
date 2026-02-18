# shadowagent

Exchange domain knowledge agents for Claude Code. Pure API/protocol knowledge for prediction markets and crypto derivatives — no pipeline or infrastructure coupling.

## Agents

| Agent | subagent_type | Focus |
|-------|--------------|-------|
| Kalshi | `shadow:kalshi` | CFTC-regulated event contracts, REST/WS API, fees, crypto tickers |
| Kraken | `shadow:kraken` | Kraken Futures perpetuals, funding rates, WebSocket API |
| Polymarket | `shadow:polymarket` | CLOB prediction market, Gamma API, token model, sharding |
| Symbology | `shadow:symbology` | Cross-exchange identifier formats, ticker anatomy |

## Installation

Add to `~/.claude/settings.json`:

```json
{
  "enabledPlugins": {
    "shadow@shadowagent": true
  }
}
```

Clone this repo to your local machine. Claude Code discovers plugins from repos in your workspace.

## Usage

Agents are available as `shadow:{name}` subagent types in Claude Code's Task tool:

```
Task(subagent_type="shadow:kalshi", prompt="Explain Kalshi fee calculation for a 50c contract")
```

These agents pair well with pipeline-specific agents (e.g., from dlawskillz) for end-to-end exchange integration work.
