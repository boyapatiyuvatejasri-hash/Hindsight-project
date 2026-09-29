# DevOps Incident Response Agent

An AI agent that remembers past incidents and resolutions using Hindsight memory, so engineers fix faster.

## What It Does

When an engineer describes a symptom (like "payment API returning 500 errors"), the agent:

1. Recalls relevant past incidents from Hindsight memory
2. Sends those incidents, plus the new symptom, to an LLM
3. Generates a diagnosis that references the team's actual history

## How Hindsight Is Used

- `memory.py` stores incidents in Hindsight using `retain()`
- Before analysis, `recall()` retrieves relevant past incidents
- The agent's diagnosis changes based on what's in memory

## Files

| File | Purpose |
|---|---|
| `app.py` | Streamlit web interface |
| `agent.py` | LLM logic + memory integration |
| `memory.py` | Hindsight memory operations |
| `data/incidents.json` | Sample incident data |

## How to Run

1. Install dependencies:
pip install streamlit groq hindsight-client python-dotenv

2. Add your API keys to `.env`:
GROQ_API_KEY=your_key_here
HINDSIGHT_API_KEY=your_key_here

3. Run:
streamlit run app.py

## Built With

- Hindsight — persistent memory for AI agents
- Groq — fast LLM inference
- Streamlit — web interface