# `.continue/` — área de trabalho em andamento (WIP)

Pasta de **rascunho de documentação e contexto** de trabalho em andamento:
roteiros de implementação, specs em discussão, notas de features que ainda
estão sendo construídas, briefings para "continuar" depois.

## Como funciona

- **Versionada no git (de propósito — NÃO está no `.gitignore`).** Assim, ao
  abrir o projeto em outra máquina/ambiente, o contexto vem junto e dá pra
  *continuar* o trabalho de onde parou.
- **Fora do build.** Nada aqui entra no APK — o Flutter empacota `lib/`,
  `assets/` e `pubspec`, não a raiz do repo. São apenas notas de dev.
- O IDE **Continue** também usa esta pasta para configuração própria.

## Convenção

Quando uma nota/roteiro **amadurece e vira doc estável**, migre para
[`/docs`](../docs/) (vision do produto em [`docs/IDEA.md`](../docs/IDEA.md),
pesquisa de scoring em [`docs/scoring.md`](../docs/scoring.md)) e remova daqui —
mantendo o `.continue/` enxuto, só com o que está realmente em andamento.

## Sobre este fork

Fork de [`akitaonrails/frank_karaoke`](https://github.com/akitaonrails/frank_karaoke).

| Remote | Aponta para |
|---|---|
| `origin` | nosso fork — `samirhvbr/FRANK_KARAOKE` |
| `upstream` | projeto original — `akitaonrails/frank_karaoke` |

Para contribuir de volta: criar branch a partir de `upstream/master`, abrir o PR
contra o **upstream**. Para sincronizar: `git fetch upstream && git merge upstream/master`.
