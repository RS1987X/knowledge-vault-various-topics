# Apps Become Forks — Thesis Notes (Chat)

**Date:** 2026-02-14  
**Context:** Notes distilled from a chat exploring the thesis that AI makes production-grade apps trivially forkable, shifting software economics toward a few canonical open-source “main branches” plus personalized forks.

---

## Thesis (as stated)

- Production-grade apps can be duplicated extremely quickly ("in an afternoon").
- Rebuilding from scratch becomes economically irrational, even if it’s trivial for AI.
- Instead of thousands of bespoke apps, we get a handful of open-source upstream repos per category.
- Agents fork the upstream and customize the experience to the individual user (or to the agent itself) based on existing context/preferences.
- **"`main` is the highway; your fork is the last-mile delivery."**
- Competitive moat shifts to:
  - number/quality of agents iterating on your repo
  - strength of feedback loops where downstream forks upstream improvements back to `main`
  - contributor “gravity” that eventually pulls maintainers of competing projects into the dominant upstream
- For agents, it’s rational to fork battle-tested code and spend compute on personalization rather than rebuilding infra/testing.
- The first principles (economics, incentives, architecture) point toward open source.
- AI makes open source not just best, but increasingly inevitable.

---

## Implications for Ethereum (ETH value capture focus)

### What the thesis is bullish on
- **Ethereum as a coordination + settlement layer**: if UX forks proliferate, shared rails become more valuable.
- **Standards + composability** increase in importance when agents stitch modular components across many forks.
- **Provenance/verification** matters more as forks multiply (which fork is authentic/trustworthy?).

### How ETH captures value (mechanisms)
1. **L1 fees burned (EIP-1559)**: ETH captures when L1 blockspace is demanded.
2. **MEV**: more economic activity increases MEV, but capture depends on where ordering happens (L1 vs L2 sequencers).
3. **Staking/security premium**: if Ethereum is the canonical settlement/provenance anchor, demand for security supports staking demand.

### Key dependency: where execution and data availability land
- Fork/agent activity likely pushes most execution to **L2s/offchain** for cost.
- ETH value capture strengthens if:
  - L2s keep posting **data availability (DA)** to Ethereum L1 at scale
  - high-value assets remain **Ethereum-issued/Ethereum-settled**
  - cross-domain interoperability continues to route through Ethereum-native standards
- ETH value capture weakens if:
  - activity migrates to **alt-DA** (validiums or non-Ethereum DA layers) widely
  - sequencing/ordering + DA + settlement drift away from Ethereum

### MEV nuance
- Fork-heavy, agent-routed finance increases MEV opportunities.
- ETH benefits directly only if a meaningful portion is captured at L1 (or if L2 sequencing is decentralized / value-shared in a way tied to ETH).

### Bottom line
- The thesis is **directionally bullish for Ethereum’s role**, but ETH value capture depends on whether Ethereum remains the dominant **DA + settlement anchor** for the rollup/agent-driven world.

---

## What else gets pulled into higher open-source development?

In a fork-first world, open sourcing accelerates wherever components are modular, widely reused, and benefit from shared QA/audits.

### Likely to see major increases
- **Agent infrastructure**: orchestration, memory, evals, guardrails, workflow DSLs.
- **Integrations/connectors (“glue code”)**: API clients, auth helpers, ETL/sync, payment/KYC adapters.
- **Verification/testing/observability**: fuzzers, sims, tracing, SBOMs, reproducible builds.
- **Security & privacy primitives**: key management wrappers, attestations, ZK libraries, selective disclosure.
- **Crypto/DeFi building blocks**: wallet libs, AA modules, oracle/risk adapters, simulation tooling.
- **Model-adjacent tooling** (even if weights stay closed): inference routing, caching, eval pipelines, dataset tooling.
- **Enterprise workflow templates**: “business processes as repos” (finops, legalops, hr ops, sales ops).
- **Robotics control software** (slower due to physical QA, but shared sims/benchmarks push openness).
- **Education artifacts**: curricula, interactive textbooks, benchmarks.
- **Gov/public digital services** (where policy permits): reusable service templates and workflows.

Common pattern: open upstream for reliability, fork downstream for personalization.

---

## Monetization in a more-open-source world

Monetization shifts from “selling code access” to selling scarce complements:

1. **Hosted/managed service**: reliability, scaling, updates, backups.
2. **Support + enterprise assurance**: SLAs, training, LTS, certified builds.
3. **Marketplace take-rates**: plugins/templates/agents/connectors.
4. **Trust/provenance/certification**: signed releases, reproducible builds, audit badges, supply-chain risk scoring.
5. **Data/network moats**: proprietary datasets, reputation graphs, fraud signals, oracle feeds.
6. **Coordination rights**: stewardship/brand/governance legitimacy.
7. **Dual licensing** (niche, can backfire depending on community norms).
8. **Usage-based micro-payments**: per-task/per-call pricing becomes more viable with agent automation.
9. **Crypto-native funding** (when real cashflows exist): bounties, grants, retroactive funding, protocol-fee-to-treasury.
10. **Insurance/guarantees**: warranties, indemnities, compliance guarantees.

What monetizes worse: charging simply for access to source code; small feature gating easily cloned by forks.

---

## Suggested next expansions
- Define what becomes the “canonical upstream” in each category (selection mechanisms).
- Explore attribution/impact measurement for upstream funding.
- Consider privacy: agent personalization vs public ledgers and surveillance.
- Sketch L1/L2 equilibrium scenarios for ETH value capture under fork-driven activity.