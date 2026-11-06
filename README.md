# ADK Python Quickstart

Personal hands-on practice following the [Agent Development Kit (ADK) Python quickstart](https://adk.dev/get-started/python/). This is a learning project, not production code.

It contains one agent, `root_agent`, which answers questions about the current time in a city using a `get_current_time` tool. The tool is a mock and always returns `10:30 AM`.

## Project structure

```text
my_agent/
├── __init__.py   # Exposes the agent module to ADK
├── agent.py      # Defines root_agent and its tool
├── .env          # API key (not committed)
└── .gitignore    # Excludes .env and .adk/
```

## Setup

Requires Python 3.10 or later. Tested with Python 3.14 and `google-adk` 2.13.0.

1. Create and activate a virtual environment, then install ADK:

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   pip install google-adk
   ```

2. Get a Gemini API key from [Google AI Studio](https://aistudio.google.com/apikey) and add it to `my_agent/.env`:

   ```bash
   echo 'GOOGLE_API_KEY="YOUR_API_KEY"' > my_agent/.env
   ```

## Run

Run these commands from the repository root.

**CLI:**

```bash
adk run my_agent
```

**Web UI** (for development and debugging only):

```bash
adk web --port 8000
```

Open <http://localhost:8000>, select `my_agent`, and ask something like `What time is it in Tokyo?`

## Difference from the quickstart

This repo uses `gemini-flash-lite-latest` instead of the quickstart's `gemini-flash-latest`, which returned `503 UNAVAILABLE` (high demand) during testing. To use the quickstart's model, change `model` in `my_agent/agent.py`.
