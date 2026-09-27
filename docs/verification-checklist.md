# Verification Checklist

Use this checklist before treating the prompt set as ready.

## Branding Removal

- No source company names.
- No source product names.
- No source model names.
- No original feedback links or support links.

## Runtime Neutrality

- No hardcoded capability names from another environment.
- No fixed shell commands in the system prompt.
- No assumption of file access in the local chat target.
- No assumption of web access unless provided by the runtime.
- No hardcoded model names in target or compiled prompts.
- Local model names are recorded only in `models.md`.

## Routing

- Code intent routes to code mode.
- Design intent routes to design mode.
- Mixed tasks use design first, implementation second.
- Ambiguous tasks ask at most one meaningful question.

## Quality

- Prompts are concise enough to fit practical context windows.
- Each file has a distinct purpose.
- Compiled targets can be used directly.
- Each `targets/*.md` file has a matching `build/compiled-*.md` file.
- Source material is transformed, not copied.
