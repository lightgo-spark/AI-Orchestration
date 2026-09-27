# LangChain Chat (langchain_gui)

A desktop LLM chat client written in pure Rust, shipped as a single executable.

### Supported providers
- **OpenAI-compatible**, **DeepSeek**, **Anthropic**, **Google Gemini**, and **Local models** (Ollama, LM Studio, llama.cpp)
- Responses stream in live over SSE

### Document RAG
- Add UTF-8 text, PDF, or HTML documents (64 documents)
- Search with **BM25 (keywords) + embeddings (meaning)**, merged with RRF; matches go into the prompt as sources
- Works fully offline and free with embeddings turned off
- Import papers straight from **arXiv** by keyword, author, or category

### Conversation summary
- Older messages that would be cut to fit the context budget are summarized and kept in the session
- Summarization cost is tracked separately; if it fails, the message is still sent

### Prompt templates
- Save a system prompt + question skeleton and load it in one click
- MCP server prompts also listed and insertable into the message box

### Tool calling
- Built-in read-only tools: `get_current_time`, `calculate`
- Optional **arXiv tools**: `arxiv_search`, `arxiv_paper` (network)
- **Approval window** before anything runs — or auto-approve all / auto-approve built-ins only
- Max rounds (1–8) caps model → tool → model round trips

### Image input
- Attach **PNG, JPEG, GIF, WebP** via file picker or drag & drop
- Recognized by file bytes, sent to vision models, shown as thumbnails
- Unsupported models are caught before sending

### Conversation management
- Pin, archive, tag, rename conversations; search by tag
- Give a conversation its own system prompt or model

### MCP servers
- Connect **Model Context Protocol** servers: local stdio commands or remote Streamable HTTP
- Their tools join the built-in ones behind the same approval window
- Per-server tool on/off list; images returned by tools reach the model

### Expert options
- **Sampling**: top_p, top_k, seed, stop sequences, penalties
- **Reasoning**: reasoning effort (OpenAI · Anthropic · DeepSeek), thinking budget (Gemini), DeepSeek thinking mode
- **Web search**: server-side search with source citations (Gemini · Anthropic · OpenAI)
- **Output**: JSON object mode, JSON schema (structured outputs), verbosity
- **Prompt caching** and per-model price table

### UI
- Premium macOS/iOS-style theme with adjustable UI scale (0.8x–2.0x)
- **UI language**: English (default) or Korean
- Thinking blocks and search sources shown separately from answers
- Clickable `http`, `https`, `mailto` links; dangerous schemes stay plain text

### Security & privacy
- API keys stored in the **OS credential manager**, never in the settings file or logs
- Conversations stored locally only — **no telemetry, no server-side components**
- Environment-variable keys are not sent to loopback addresses (prevents key leaks to local servers)

### Bonus
- **bench.exe** — compares latency, throughput, and cost across endpoints
- Single executable: no web view, no bundled runtime

### Credits & open source
- **LangChain** — the app's name and concept take after the open-source [LangChain] project (MIT License) by LangChain, Inc. This app is an independent project and is **not affiliated with or endorsed by** LangChain, Inc.