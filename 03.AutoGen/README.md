# AutoGen Workbench

## Key Features

- **Multi-agent team**: AssistantAgent + CodeExecutorAgent, RoundRobin (sequential) / Selector (LLM-chosen) modes
- **Termination conditions**: `TextMentionTermination("TERMINATE")` + `MaxMessageTermination`, plus Timeout · TokenUsage · SourceMatch
- **LLM integration**: OpenAI-compatible · Anthropic Messages · Azure OpenAI, SSE streaming, retry/backoff, cancellation token, token usage tracking
- **Model selection**: Provider dropdown (OpenAI·DeepSeek·Claude·Gemini·Grok·OpenRouter·Azure·Ollama·LM Studio·custom), automatic model list fetching, connection test, Temperature · max tokens
- **API key management**: Environment variable auto-detection, in-memory session keys, optional DPAPI-encrypted storage
- **Built-in tools (function calling)**: Time · workspace list/read/write/search, approval gate, path-escape blocking (OpenAI · Anthropic native)
- **Code execution**: Local/Docker Python, timeout · output limits, human approval, artifact detection
- **Sandbox**: Local (network-blocking sitecustomize) / Docker (`--network none`, memory·CPU·PID limits)
- **Artifact viewer**: Image · CSV table · text/JSON preview, open in Explorer
- **Premium UI**: Dark/light theme, 3-pane layout, resizable panels · UI scale, Korean/English toggle, Markdown + Python highlighting
- **Observability**: Dashboard (turns·tokens·cost·progress), agent status cards, control-flow graph, event log, file logs · run history
- **Workspace**: Session CRUD · autosave · resume, continue conversation, edit-and-rerun, TaskResult JSON/Markdown export
- **Reliability**: Worker panic detection, pause/resume, external termination, atomic session saves

### License & Copyright

This project is an independent implementation inspired by Microsoft AutoGen's AgentChat (v0.4). AutoGen's code packages are licensed under the MIT License (Copyright (c) Microsoft Corporation).  Not affiliated with or endorsed by Microsoft.
