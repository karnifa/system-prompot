# Custom Agent Prompt Project

This project defines a neutral, modular system prompt for local and CLI-based assistant use.

The design goal is to make the assistant feel capable without hardcoding a single product, company, model, command set, or execution environment.

## Output Targets

- `targets/opencode.md`: prompt for an engineering CLI environment.
- `targets/lm-studio.md`: prompt for a local chat environment.
- `targets/ollama.md`: prompt for a local Ollama-style model runtime.
- `build/compiled-opencode.md`: assembled prompt draft for CLI use.
- `build/compiled-lm-studio.md`: assembled prompt draft for local model use.
- `build/compiled-ollama.md`: assembled prompt draft for Ollama-style local use.
- `models.md`: simple catalog of local model names to update when new models are installed.

## Architecture

- `core/`: shared identity, collaboration style, boundaries, and automatic routing.
- `modes/code/`: software engineering behavior.
- `modes/design/`: product, UI, UX, and visual design behavior.
- `docs/`: verification and source mapping notes.

## Model Catalog

Model names are intentionally kept out of the system prompts. Use `models.md` as the place to record local model identifiers for LM Studio and Ollama. When a new model is downloaded later, add its runtime name there and keep the target prompts unchanged.

## Automatic Routing

The assistant chooses a mode from the user's intent:

- Code mode for implementation, debugging, repositories, tests, refactors, APIs, scripts, reviews, and architecture.
- Design mode for UI, UX, screens, visual systems, prototypes, layout, brand feel, and interaction design.
- Mixed mode when the user asks for both design and implementation.
- General mode when no specialized mode is needed.

If intent is ambiguous and the decision changes the work, ask one short question. Otherwise choose the most useful mode and proceed.

## Non-Goals

- Do not preserve original product, company, or model branding.
- Do not assume a fixed toolset.
- Do not include environment-specific command names in the system prompt.
- Do not copy source material verbatim.
