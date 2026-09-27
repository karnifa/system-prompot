# Local Model Catalog

Use this file to record model names available in local runtimes. The prompts do not bind themselves to a specific model; change models in LM Studio or Ollama normally.

When you download a new model, copy one of the examples below, paste it in the right section, and change the values.

## LM Studio

LM Studio models are stored locally under `C:\Users\pauli\.lmstudio\models`.

### Gemma4 26B A4B Uncensored HauhauCS Balanced

- Runtime: LM Studio
- Folder: `HauhauCS\Gemma4-26B-A4B-Uncensored-HauhauCS-Balanced`
- Main file: `Gemma4-26B-A4B-Uncensored-HauhauCS-Balanced-Q4_K_M.gguf`
- Notes:

### Gemma 4 12B IT QAT

- Runtime: LM Studio
- Folder: `lmstudio-community\gemma-4-12B-it-QAT-GGUF`
- Main file: `gemma-4-12B-it-QAT-Q4_0.gguf`
- Notes:

### Qwen3.8 27B

- Runtime: LM Studio
- Folder: `lmstudio-community\Qwen3.8-27B-GGUF`
- Main file: `Qwen3.8-27B-Q4_K_M.gguf`
- Notes:

To add a new LM Studio model:

1. Download or import the model in LM Studio.
2. Find the new folder under `C:\Users\pauli\.lmstudio\models`.
3. Copy this block and paste it above the instructions:

```md
### New model name

- Runtime: LM Studio
- Folder: `creator-or-source\model-folder`
- Main file: `model-file.gguf`
- Notes:
```

4. Replace the title, folder, and main `.gguf` file.
5. Ignore `mmproj-*.gguf` files unless you specifically need to document multimodal projector files.

## Ollama

Add model names exactly as Ollama expects them. These are the names you can use with `ollama run <name>`.

OpenCode uses the `128k` variants below. To switch OpenCode's default model, edit `C:\Users\pauli\.config\opencode\opencode.json` and change only `model` or `small_model`.

Available OpenCode model values:

```text
ollama/qwen3.8:27b-128k
ollama/gemma4:12b-128k
ollama/gemma4:26b-128k
ollama/qwen3.8-hauhaucs:128k
```

### Qwen3.8 27B Uncensored HauhauCS Aggressive

- Runtime: Ollama
- Name: `qwen3.8-hauhaucs:128k`
- Size: 18 GB
- Run with: `ollama run qwen3.8-hauhaucs:128k`
- Notes: 128k variant for OpenCode, created from `aiconjured/Qwen3.8-27B-Uncensored-HauhauCS-Aggressive-MTP-GGUF-Q8-NVFP4:latest`.

### Gemma4 26B

- Runtime: Ollama
- Name: `gemma4:26b-128k`
- Size: 18 GB
- Run with: `ollama run gemma4:26b-128k`
- Notes: 128k variant for OpenCode, created from `gemma4:26b`.

### Qwen3.8 27B

- Runtime: Ollama
- Name: `qwen3.8:27b-128k`
- Size: 17 GB
- Run with: `ollama run qwen3.8:27b-128k`
- Notes: 128k variant for OpenCode, created from `qwen3.8:27b`.

### Gemma4 12B

- Runtime: Ollama
- Name: `gemma4:12b-128k`
- Size: 7.6 GB
- Run with: `ollama run gemma4:12b-128k`
- Notes: 128k variant for OpenCode, created from `gemma4:12b`.

To add a new Ollama model:

1. Install it with Ollama.
2. Run `ollama list`.
3. Copy the exact value from the `NAME` column.
4. Copy this block and paste it above the instructions:

```md
### New model name

- Runtime: Ollama
- Name: `ollama-model-name:tag`
- Size:
- Run with: `ollama run ollama-model-name:tag`
- Notes:
```

5. Replace the title, `Name`, size, and `Run with` command.

To create a 128k OpenCode-friendly variant:

1. Create a Modelfile with:

```md
FROM original-model-name:tag
PARAMETER num_ctx 131072
```

2. Create the new tag:

```powershell
ollama create new-model-name:128k -f path\to\Modelfile
```

3. Add the new tag to `C:\Users\pauli\.config\opencode\opencode.json` with:

```json
"limit": {
  "context": 131072,
  "output": 16384
}
```

## Notes

- Keep this file as the only model-name catalog.
- Do not add model names to `core/`, `modes/`, or compiled prompts unless a target genuinely requires it.
- If a model needs special prompting behavior, document that as a note here before changing shared prompt behavior.
