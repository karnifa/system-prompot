# OpenCode + Ollama

OpenCode does not automatically inherit the model list or context settings from this project's `models.md`.

Local OpenCode config lives at:

`C:\Users\pauli\.config\opencode\opencode.json`

## Current Setup

OpenCode is configured to use Ollama through the OpenAI-compatible endpoint:

`http://localhost:11434/v1`

The source-controlled template is:

`opencode/opencode-ollama-128k.json`

The live OpenCode config is:

`C:\Users\pauli\.config\opencode\opencode.json`

## Changing Models

To change the default model, edit only this line in the live config:

```json
"model": "ollama/qwen3.8:27b-128k"
```

To change the smaller helper model, edit only this line:

```json
"small_model": "ollama/gemma4:12b-128k"
```

Use one of these values:

```text
ollama/qwen3.8:27b-128k
ollama/gemma4:12b-128k
ollama/gemma4:26b-128k
ollama/qwen3.8-hauhaucs:128k
```

Default model:

`ollama/qwen3.8:27b-128k`

Small model:

`ollama/gemma4:12b-128k`

## Context Length

For OpenAI-compatible clients, do not rely only on the base model's maximum context length. Create an Ollama model variant with `PARAMETER num_ctx 131072`, then configure OpenCode with an explicit model limit.

Each OpenCode model entry should include:

```json
"limit": {
  "context": 131072,
  "output": 16384
}
```

When adding a new model, there are three places to update:

1. Create the Ollama `128k` tag with a Modelfile in `ollama/`.
2. Add the model entry to `C:\Users\pauli\.config\opencode\opencode.json`.
3. Add the same entry to `opencode/opencode-ollama-128k.json` so this repo stays reproducible.

## Verify

List Ollama models:

```powershell
ollama list
```

Confirm a model has 128k context:

```powershell
ollama show qwen3.8:27b-128k
```

Confirm OpenCode sees the models and limits:

```powershell
cmd /c opencode.cmd models ollama --verbose
```
