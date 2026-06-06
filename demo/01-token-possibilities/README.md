# Token Possibilities

Token Possibilities is a Shiny (R) app that makes the **one-token-at-a-time**
nature of language models visible. It sends your prompt to a model, then renders
the response token by token, coloring each token by the model's confidence.
Click any token to see the **top alternative tokens** the model considered at
that position and their probabilities.

It is a teaching tool for the "how LLMs work" part of the workshop: it shows that
generating text is repeated probabilistic next-token prediction, and that the
words in your prompt shift those probabilities.

## Why this demo uses OpenAI (not Anthropic)

This is the one demo in the workshop that runs on **OpenAI** instead of
Anthropic. The visualization depends on per-token **log probabilities**
(`logprobs` / `top_logprobs`), which OpenAI's API exposes but Anthropic's API
does not. There is no equivalent on Claude, so the alternative-token view cannot
be built there.

In practice this is an **instructor-run demo**: run it from your own OpenAI
account during the session. Participants only need Anthropic access for the rest
of the workshop and do not need to run this app themselves.

## Requirements

- R, with these packages: `shiny`, `bslib`, `dplyr`, `purrr`, `scales`, `rlang`,
  `bsicons`, `shinychat`, and `ellmer` (plus `httr2`, which `ellmer` depends on).
- An OpenAI API key in the `OPENAI_API_KEY` environment variable, for example in
  your `.Renviron`. `ellmer` reads it automatically.

## Running

From R, in this directory:

```r
shiny::runApp()
```

Type a prompt, press **Submit**, and explore the token colors and the
click-to-reveal alternatives. The **Ideas** tab (`ideas.md`) has prompts to try,
such as swapping `cat` for `animal`, or ambiguous openers like "The bank...".

The app calls `gpt-4.1-nano` by default; you can change the model in `app.R`.
Note that it relies on OpenAI's Responses API as exposed by current `ellmer`, so
the logprobs are read from the response's `output_text` content part.

## Credit

Adapted from [work by Garrick Aden-Buie](https://github.com/posit-conf-2025/llm/tree/main/_demos/04_token-possibilities).

## License

MIT License, see the LICENSE file for details.
