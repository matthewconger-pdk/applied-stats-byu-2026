# Clearbot

Clearbot is a chatbot UI designed to illustrate a few features of LLM APIs. It is built using [Shiny](https://shiny.posit.co/) (Python) and Chatlas.

It has three main features:

1. Allows you to set the system prompt and other parameters.
2. Has toggle-able tools for weather, filesystem access, and web search.
3. Lets you inspect the underlying JSON request/response data.

## Requirements

You can either set these environment variables manually, or include a [`.env` file](https://saurabh-kumar.com/python-dotenv/) in the root directory of your project.

The following environment variable is **required**:

- `ANTHROPIC_API_KEY` - Used to access Anthropic LLM models.

## Usage

Using uv:

```python
uv run shiny run app.py
```

Alternatively, use `uv sync` to install the app's dependencies in a virtual environment, and then run the app with `shiny run app.py` (or using VS Code or Positron with the Shiny VS Code extension).

## Credit

Adapted from [work by Garrick Aden-Buie](https://github.com/posit-conf-2025/llm/tree/main/_demos/03_clearbot).

## License

MIT License, see the LICENSE file for details.
