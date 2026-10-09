# Rodion Agafonov

Performance-marketing operator, 12+ years. I currently run ~$600K/month of Meta ad spend in-house as a single operator — about 5,000 active ads — with analysis, creative iteration, and anomaly detection carried by LLM workflows I build myself. Since I took over, lead-to-booking conversion went from 5% to 14%. Before this: Head of Operations at SoMin.ai, an AI ad-optimization platform serving 30 enterprise clients. Before that: built the paid-social department at Mindshare/WPP from zero to 7 people covering 40+ brands at ~$7.7M/yr.

---

## How I run marketing with agents

The operating rule: agents get the judgment calls; deterministic code gets the load-bearing decisions — money, deletion, spend. **The LLM never touches the money.**

- Agents read, cluster, rank, and flag. 5,000 active ads is not a human-scale reading job.
- Code executes. Budget changes, pauses, deletions — anything irreversible runs through tested deterministic paths, never through a model's output.
- Nothing is autonomous by default. Every workflow climbs a trust ladder: backtest → shadow mode → human-in-the-loop → bounded autonomy.
- A workflow moves up a rung only after I have watched it be wrong and priced what that costs.
- Changes are pinned against a golden corpus, so a "better" prompt that breaks old cases fails loudly before it ships.

---

## What's in the repos

[**marketing-agent-pipeline**](https://github.com/rodion-whatisai/marketing-agent-pipeline) — the pipeline behind the numbers above: tracking-audit scanner, competitor ad intelligence, spend estimation, and the golden-corpus regression harness.

Smaller tools from the same practice, each an anonymized extract from a private working repo:

- [**targeting-tree**](https://github.com/rodion-whatisai/targeting-tree) — a Meta ad account drawn as a tree and grown day by day: thickness is spend, colour is CPL against the median, two periods side by side with a scoreboard. One HTML file, demo on synthetic data.
- [**lead-autorouter**](https://github.com/rodion-whatisai/lead-autorouter) — deterministic CRM lead router: write-proxy guards, undo, 198 offline tests, no LLM in the loop.
- [**creative-precull**](https://github.com/rodion-whatisai/creative-precull) — Claude-vision agent that culls a photo dump down to the frames usable behind ad copy. The model grades, a human picks.
- [**agent-outbox**](https://github.com/rodion-whatisai/agent-outbox) — sandboxed agents deliver reports to Telegram without ever holding credentials.
- [**youtube-brief**](https://github.com/rodion-whatisai/youtube-brief) — video → local Whisper transcript → structured summary.

The working language of the repos is Russian; the READMEs are in English.

In production since July 2026, not public (account-specific, client data): a media planner that rebuilds per-city budgets every morning from studio capacity and the booking book: every step from lead to arrival measured per city and channel×targeting cell, a walk-forward model refit every Monday behind five pre-registered gates (a red gate keeps the last green model), and per-ad-set budget recommendations optimised on cost per booking and cost per arrival, which closes about three months after the lead; a weekly metrics matrix on the warehouse gold tables with per-source freshness edges; a cross-system lead dossier by phone number; daily call lists per agent, built and scored by fixed rules. The pattern is the same in each: code decides what is checkable, a gate decides whether anything ships, a person decides the rest.

If you are an engineer checking whether the marketing guy actually writes code: start with the regression harness.

---

## Contact

[linkedin.com/in/agafonov-rodion](https://www.linkedin.com/in/agafonov-rodion)
