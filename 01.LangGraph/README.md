# LangGraph Studio 

**A desktop application to design, run, and operate LangGraph-based AI workflows on a canvas.**

Build AI pipelines just by dragging and dropping nodes and connecting them.
The Python backend and the Rust backend run on the same API contract, while the Rust (egui) desktop app handles the UI and execution.


## Key Features

### 1. Canvas Workflow Editing
- **Create · connect · delete · rename nodes** on the canvas, with auto layout, minimap, and zoom/fit
- **16 built-in nodes**
  - AI: Planner · Researcher · Writer · Reviewer · Extract · Map
  - Flow: Router · Human review · Finalizer · Subgraph
  - Data: Template · Transform · Memory · File Analysis · Web Page · HTTP Request
- Add **custom nodes**
- Conditional branching: 10 rule types (JSON path comparison) or **AI classification**
- **Parallel execution** (fan-out) and joins (join any / all)
- Workflow **version history · diff · restore**

### 2. AI
- **14 AI providers**: OpenAI · Anthropic · Gemini · DeepSeek · Groq · Mistral · xAI · OpenRouter · Together · Azure OpenAI · Ollama · LM Studio · vLLM · Mock 
- Set a **different provider · model · temperature per node**
- API keys are stored in the **Windows Credential Manager** (never in plain text in config files)
- Test LLM connections before running, and list available models per provider

### 3. Execution & Operations
- Run · **cancel** · **resume from checkpoint**, recover interrupted runs after a crash
- **Real-time SSE streaming** for per-node status · output · duration
- Run history · audit log · trace spans · Prometheus metrics
- **Scheduler** (interval) and **inbound webhook** triggers
- **Evals**: batch-run datasets + scoring + summary

### 4. Security & Reliability
- Bearer token authentication — 3 roles (viewer / operator / admin), workspace isolation
- HTTP node allowlist · host re-validation at run time · size limits
- Concurrent run cap · SSE connection cap · retention TTL policies

### 5. Desktop Experience
- **Run and manage the local Python / Rust backend directly from the app** (remote server connection also supported)
- Shortcuts (`Ctrl+Enter` run, `Esc` cancel, `F` fit, `L` auto layout), canvas layout auto-saved
- Node click inspector · hover tooltips · bottom status bar

## Layout

| Path | Description |
| --- | --- |
| `rust-gui/` | Desktop GUI — Rust, eframe/egui |
| `backend/` | Backend — Python, FastAPI + LangGraph |
| `backend-rs/` | Backend — Rust, axum + rusqlite (same API contract) |


## Copyright

The licenses of the open-source libraries used (LangGraph, egui, etc.) follow their respective projects.