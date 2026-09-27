# BeeAI

A desktop GUI for a three-stage multi-agent writing pipeline that runs on local
Ollama models or OpenAI-compatible APIs (DeepSeek, OpenAI, custom endpoints).

Query in → **Researcher → Critic → Editor** → polished report out.

## Features

### Multi-Agent Pipeline
- **Researcher** gathers structured notes, **Critic** finds weaknesses, and
  **Editor** produces the final draft — each stage streams its output live.
- Structured research output with per-step token/latency metrics.
- Retry with backoff on transient errors, cancellation at any time, and
  reasoning capture for thinking models.
- Optional tool use: the model can call `http_get` to fetch web content
  during research.
- Session memory: previous run notes carry over to follow-up queries.
- User-editable prompt templates for all three stages
  (`{query}`, `{notes}`, `{critique}` placeholders).

### Models & Providers
- Works with local **Ollama** and any **OpenAI-compatible** API
  (DeepSeek, OpenAI, or a custom base URL).
- Provider presets with per-preset base URL, default model, and API key.
- Model picker with search filter, model count, and details
  (parameter count / quantization / size).
- Adjustable temperature and structured-output toggle.

### User Interface
- Four views: Researcher, Critic, Editor, and a combined report tab.
- Markdown rendering with tables, plus a JSON view of each stage.
- Dark / light / system themes.
- English localization.
- Keyboard shortcuts (e.g. `Ctrl + 1…4` to switch tabs), toasts, and a
  built-in help window.

### Results & History
- Export results to **Markdown, JSON, plain text, and PDF**
  (PDF embeds a subsetted system font so Korean text renders correctly).
- SQLite-backed run history with schema versioning and RON migration.

### Security
- API keys are stored in the **Windows Credential Manager**, shown masked,
  and never written to settings files.

### CLI & Tooling
- CLI mode: `--cli "<query>"` with `--provider`, `--model`, `--base-url`,
  `--temperature`, `--tools`, `--no-structured`.
- Key management: `--set-api-key`, `--delete-api-key`, `--profile`.
- Update checker: `--check-update <manifest-url>`.
- Local activity log with daily rotation and panic backtraces.
- Windows installer (Inno Setup) and a packaging script.
- CI quality gate: rustfmt, clippy (`-D warnings`), tests, release build.

## Requirements

- Rust 1.88+ (edition 2021)
- Ollama running locally and/or an API key for an OpenAI-compatible provider
- Windows is the primary target (installer, credential manager integration)

## Version

0.1.0

## License & Copyright

This product includes software developed by IBM Research
as part of the BeeAI Framework licensed under the Apache License, Version 2.0.