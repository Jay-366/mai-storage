# mai-storage — Career-Ops Multi-Agent

A multi-agent job-search assistant built with Streamlit and DeepSeek. Inspired by
[career-ops](https://github.com/santifer/career-ops), rebuilt as genuine multi-agent:
a central Orchestrator agent (LLM tool-use) delegates to specialist tools — some
deterministic Python, some narrow-scoped LLM sub-agents.

See `.claude/plans/delegated-knitting-bentley.md` for the full build plan.

## Milestone 1 scope

Scan real job postings (Greenhouse, Ashby, Lever, Recruitee) → evaluate fit against
your CV → draft a tailored cover letter + application answers → research the company
→ prep interview stories → track status. Output is a human-reviewed "ready to apply"
package; actually submitting is a deliberate manual step (submission automation is a
later milestone).

## Setup

```
pip install -r requirements.txt
cp .env.example .env   # fill in DEEPSEEK_API_KEY and TAVILY_API_KEY
```

Edit `config/profile.yml`, `cv.md`, and `config/story_bank.yml` with your real
background — these are the source-of-truth inputs every agent reads from and must
never fabricate beyond.

```
streamlit run app.py
```
