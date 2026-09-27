# Local Model Catalog

Use this file to record model names available in local runtimes. The prompts do not bind themselves to a specific model; change models in LM Studio or Ollama normally.

When you download a new model, add the exact runtime name here.

## LM Studio

Add model display names or local identifiers as they appear in LM Studio.

- Example: `local-model-name`

## Ollama

Add model names exactly as Ollama expects them.

- Example: `llama3.1:8b`

## Notes

- Keep this file as the only model-name catalog.
- Do not add model names to `core/`, `modes/`, or compiled prompts unless a target genuinely requires it.
- If a model needs special prompting behavior, document that as a note here before changing shared prompt behavior.
