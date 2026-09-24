# Claude Code configuration — frank_karaoke (fork)

## Model
The user's choice, made per session with `/model`; subagents inherit the
session's model. This repository sets none of it — `.claude/settings.json`
carries no model key and no model environment variable (repodocs ADR-027).

## Effort
`max` + adaptive thinking off (deep reasoning at all times).

## Critical permissions (Flutter/Dart)
- `flutter analyze` / `flutter test` allowed — **always validate before saying "done"**
  (rule from `../CLAUDE.md`: check with analyze + test + device before concluding).
- `git push --force`, `git reset --hard`, `git clean -fd` **blocked** — history protection.
- Reading Android signing secrets **blocked** (`android/key.properties`, `*.jks`, `*.keystore`).
- Touching dependencies is in `ask` mode — `flutter pub upgrade` / `pub add` / `pub upgrade` require confirmation.
- `defaultMode: plan` — Claude plans before editing.

## Project rules (summary of `../CLAUDE.md`)
- **Android-only**: no Linux desktop support (WebView + mic are Android-specific).
- **Phased execution**: max. 5 files per phase; verify before the next one.
- **Research before implementing**: for non-trivial features, present a plan before coding.
