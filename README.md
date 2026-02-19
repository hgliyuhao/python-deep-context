
# Python Deep-Context

**Send your LLM only what matters. Not entire files.**

Connectivity-aware context extraction for serious Python workflows.

![Version](https://img.shields.io/visual-studio-marketplace/v/DeepContextLabs.python-deep-context)  
![Installs](https://img.shields.io/visual-studio-marketplace/i/DeepContextLabs.python-deep-context)  
![Rating](https://img.shields.io/visual-studio-marketplace/r/DeepContextLabs.python-deep-context)  
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

---

## What this extension does

Python Deep-Context builds a **precise, token-budgeted context report** around the symbol you're working on.

Instead of pasting entire files into ChatGPT or Copilot, you get:

- exact dependencies  
- real call-site evidence  
- behavior signals  
- minimal token footprint  

It runs a **local Sidecar Engine** that performs hybrid static + LSP analysis and outputs a clean Markdown artifact ready for any LLM.

No cloud.  
No indexing server.  
No config.

---

## Why developers install this

Most LLM failures come from context problems:

| Problem | Result |
|--------|-------|
Too much code | token waste, hallucinations |
Too little code | wrong assumptions |
Missing call context | broken refactors |
Hidden side-effects | unsafe edits |

Deep-Context fixes this by generating a **high-signal connectivity slice** around your current symbol.

The LLM receives only what it needs to reason correctly.

---

## Demo

![Demo](https://github.com/hgliyuhao/python-deep-context/raw/HEAD/media/demo.gif)

---

## Core benefits

### High-signal context
Only the definitions and call-paths that matter.

### Fully local
Runs entirely on your machine.  
Your code never leaves VS Code.

### Zero setup
Engine is bundled.  
Works out-of-the-box.

### Fast
AST fast-path first.  
LSP when needed.  
Text fallback if required.

### Works with any LLM
ChatGPT  
Claude  
Copilot Chat  
Cursor  
Continue  
Custom agents

---

## Quick start

### 1. Start engine
Open Command Palette:

```

Deep-Context: Start Engine

```

---

### 2. Generate report
Right-click inside Python file:

```

Deep-Context: Generate Report (Here)
Deep-Context: Generate Report (Selection)

```

---

### 3. Send to LLM
```

Deep-Context: Copy Last Report Markdown

````

Paste into your chat tool.

You now get **correct answers with far fewer tokens**.

---

## What makes it different

### Connectivity-aware slicing
Resolves local helper functions, types, and callers  
(1-hop dependency closure)

### Hybrid analysis
AST + LSP + textual verification  
Fast when possible, precise when needed.

### Token budgeting
Output size is strictly controlled.  
Core logic preserved. Noise collapsed.

### Behavior signals
Highlights:
- I/O
- mutations
- network calls
- external APIs

LLMs reason better when behavior is visible.

---

## Who this is for

Python engineers using:

- ChatGPT for refactoring
- Copilot Chat
- Claude
- Cursor / Continue
- custom coding agents
- large codebases
- monorepos

If you paste code into LLMs daily, this saves time and tokens.

---

## Requirements

- VS Code Python extension (`ms-python.python`)
- Python workspace

Nothing else.

No pip installs required.

---

## Troubleshooting

**Empty report**  
Wait for Python extension indexing to finish.

**Missing cross-file links**  
Ensure correct interpreter is selected.

**Ripgrep error (Windows)**  
Ensure `rg` exists in PATH.

---

## Architecture (short version)

Layered pipeline:

1. AST fast path  
2. LSP symbol linking  
3. dependency environment scan  
4. side-effect detection  
5. token allocator  

All local.  
No cloud indexing.

---

## For agent developers

Deep-Context outputs:

- machine-readable JSON header  
- Markdown body  

This allows automated pipelines and tools to consume context programmatically.

```json
{
  "v": 2,
  "target": { "file": "api.py", "line": 42 },
  "sections": ["deps_used", "callers", "source"]
}
````

---

## Roadmap

* connectivity graph view
* patch/diff hints
* MCP integration
* token presets for major LLMs
* multi-file context mode

---

## License

MIT

---

## Links

[Report Bug](https://github.com/hgliyuhao/python-deep-context/issues)
[Request Feature](https://github.com/hgliyuhao/python-deep-context/issues)


```

