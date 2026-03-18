# CostGate

Control how much your AI can spend.

CostGate is a lightweight API that enforces **LLM cost budgets** for your applications.

🌐 Website: https://costgate.dev


## Example
```javascript
const check = await fetch("https://api.costgate.dev/v1/check", {...})

if (!check.isAllowed) throw new Error("Budget exceeded")

// call LLM

await fetch("https://api.costgate.dev/v1/consume", {...})
```
check → call LLM → consume

## What you get
- per-user budgets
- per-feature budgets
- per-project budgets
- policy engine (allow / block / downgrade)
- Redis-based high-speed checks


Examples:
- $10/day per user
- $100/day per feature
- block requests when exceeded

Works with:
OpenAI • Anthropic • Mistral • Gemini • Claude • OpenRouter • Any LLM


## Why CostGate

LLM usage can easily spiral out of control.

Examples:

- AI agents stuck in prompt loops
- unexpected traffic spikes
- per-user abuse
- runaway background jobs

CostGate adds **cost-based enforcement** in front of your LLM calls.


## How it works

Typical flow:

1️⃣ Check budget
POST /v1/check

2️⃣ Call the LLM

3️⃣ Record usage
POST /v1/consume


## Example integrations

See [/examples](./examples/).

## API

See [openapi.yaml](./openapi.yaml).

## Early access

If you want to try it:

- comment / DM
- or visit https://costgate.dev
