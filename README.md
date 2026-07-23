# Rodion Agafonov

Performance-marketing operator, 12+ years. I currently run ~$600K/month of Meta ad spend in-house as a single operator — about 5,000 active ads — with analysis, creative iteration, and anomaly detection carried by LLM workflows I build myself. Since I took over, lead-to-booking conversion went from 5% to 14%. Before this: Head of Operations at SoMin.ai, an AI ad-optimization platform serving 30 enterprise clients. Before that: built the paid-social department at Mindshare/WPP from zero to 8 people covering 40 brands at ~$7.7M/yr.

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

The working language of the repo is Russian; the README is in English.

Also in production, not public: a lead-router with 190 offline tests, and a Claude-vision creative pre-selector that grades creatives before they spend a dollar.

If you are an engineer checking whether the marketing guy actually writes code: start with the regression harness.

---

## Contact

[linkedin.com/in/agafonov-rodion](https://www.linkedin.com/in/agafonov-rodion)
