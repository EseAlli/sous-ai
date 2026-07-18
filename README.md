# sous-ai - Gradio Chat

A simple streaming chat web app built with [Gradio](https://www.gradio.app/) and powered by the [OpenRouter](https://openrouter.ai/) API. The chatbot acts as a cooking assistant: it helps with recipes, ingredient substitutions, and nutritional information across a variety of cuisines.

## Screenshot

![SizzleChat screenshot](screenshot.png)

## Requirements

- Python 3.10+
- An OpenRouter API key (free tier works with the `openrouter/free` model)

## Setup

This project uses [uv](https://docs.astral.sh/uv/) for dependency and environment management.

1. Install uv (if you haven't already):

   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

2. Create a `.env` file in the project root with your OpenRouter API key:

   ```bash
   cp .env.example .env
   ```

   Then edit `.env`:

   ```
   API_KEY=sk-or-v1-...your-key-here
   ```

   You can create a free key at https://openrouter.ai/keys.

3. Install dependencies and create the virtual environment:

   ```bash
   uv sync
   ```

   This reads `requirements.txt` (or `pyproject.toml` if you add one) and sets up `.venv`.

## Running

```bash
uv run app.py
```

Gradio will start a local server (typically http://127.0.0.1:7860) and open the chat interface in your browser.

## Project layout

```
.
├── app.py            # Gradio chat app + OpenRouter client
├── requirements.txt  # Python dependencies
├── .env              # API key (gitignored, do not commit)
└── .gitignore
```

## Notes

- `.env` and `.venv/` are gitignored. Never commit your API key.
- To use a different model, change `MODEL` in `app.py` (e.g. `openai/gpt-4o-mini`).
