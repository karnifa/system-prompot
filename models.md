# Local Model Catalog

Use this file to record model names available in local runtimes. The prompts do not bind themselves to a specific model; change models in LM Studio or Ollama normally.

When you download a new model, add the exact runtime name here.

## LM Studio

LM Studio models are stored locally under `C:\Users\pauli\.lmstudio\models`.

Current models:

| Display name | Local path | Main model file |
| --- | --- | --- |
| Gemma4 26B A4B Uncensored HauhauCS Balanced | `HauhauCS\Gemma4-26B-A4B-Uncensored-HauhauCS-Balanced` | `Gemma4-26B-A4B-Uncensored-HauhauCS-Balanced-Q4_K_M.gguf` |
| Gemma 4 12B IT QAT | `lmstudio-community\gemma-4-12B-it-QAT-GGUF` | `gemma-4-12B-it-QAT-Q4_0.gguf` |
| Qwen3.8 27B | `lmstudio-community\Qwen3.8-27B-GGUF` | `Qwen3.8-27B-Q4_K_M.gguf` |

To add a new LM Studio model:

1. Download or import the model in LM Studio.
2. Find the new folder under `C:\Users\pauli\.lmstudio\models`.
3. Add one row above with the display name, local path, and main `.gguf` file.
4. Ignore `mmproj-*.gguf` files unless you specifically need to document multimodal projector files.

## Ollama

Add model names exactly as Ollama expects them. These are the names you can use with `ollama run <name>`.

Current models:

| Runtime name | Size | Notes |
| --- | ---: | --- |
| `aiconjured/Qwen3.8-27B-Uncensored-HauhauCS-Aggressive-MTP-GGUF-Q8-NVFP4:latest` | 18 GB | Installed in Ollama |
| `gemma4:26b` | 18 GB | Installed in Ollama |
| `qwen3.8:27b` | 17 GB | Installed in Ollama |
| `gemma4:12b` | 7.6 GB | Installed in Ollama |

To add a new Ollama model:

1. Install it with Ollama.
2. Run `ollama list`.
3. Copy the exact value from the `NAME` column.
4. Add one row above using that exact runtime name.

## Notes

- Keep this file as the only model-name catalog.
- Do not add model names to `core/`, `modes/`, or compiled prompts unless a target genuinely requires it.
- If a model needs special prompting behavior, document that as a note here before changing shared prompt behavior.
