# Council

Ask one question and two AIs work it out. Claude and Gemini each answer on their own with web search, check each other's work, fix only what matters, then merge into one final answer that lists where they still disagree and how confident they are.

**Open the app:** https://mrbooty42.github.io/council/

## How it works
1. **Opening:** both models answer independently.
2. **Review:** each one checks the other's answer, agrees with what's right, and flags only problems that matter (including weak sources).
3. **Revise:** each takes the good points and improves its answer. Skipped when neither review finds a real problem. Quick runs at most one round, Standard two, Deep three, and it stops as soon as they agree on the substance.
4. **Verdict:** one model merges the best of both into a single answer. It favors a few strong primary sources over many weak ones, and the source list shows only what the answer actually cites.

**Power:** Auto (default) has a tiny model read each question and pick Economy (Claude Sonnet 5.5 + Gemini 3.8 Flash) for everyday questions or Max (Claude Opus 5.5 + Gemini 4 Argon) for hard or high-stakes ones. You can also force Economy or Max.

Also: PDF, Word, PowerPoint and photo uploads; solo mode (one model, much cheaper); a monthly spend tracker; Download for Word; history backup.

## Privacy
The app is one HTML file that runs in your browser. Your API keys and history are stored only in that browser. Questions go straight from your browser to Anthropic and Google. No other server is involved, and nothing private is stored in this repository.
