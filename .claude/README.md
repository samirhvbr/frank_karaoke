# Configuração Claude Code — frank_karaoke (fork)

## Modelo
`opus` (Opus 4.8) em tudo, com janela de **1M** de contexto. Subagents também em Opus.

## Effort
`max` + adaptive thinking off (raciocínio profundo sempre).

## Permissões críticas (Flutter/Dart)
- `flutter analyze` / `flutter test` liberados — **sempre validar antes de "done"**
  (regra do `../CLAUDE.md`: verificar com analyze + test + device antes de concluir).
- `git push --force`, `git reset --hard`, `git clean -fd` **bloqueados** — proteção do histórico.
- Leitura de segredos de assinatura Android **bloqueada** (`android/key.properties`, `*.jks`, `*.keystore`).
- Mexer em dependências em modo `ask` — `flutter pub upgrade` / `pub add` / `pub upgrade` pedem confirmação.
- `defaultMode: plan` — Claude planeja antes de editar.

## Regras do projeto (resumo de `../CLAUDE.md`)
- **Android-only**: sem suporte a desktop Linux (WebView + mic são específicos de Android).
- **Execução em fases**: máx. 5 arquivos por fase; verificar antes da próxima.
- **Pesquisar antes de implementar**: para features não triviais, apresentar plano antes de codar.
