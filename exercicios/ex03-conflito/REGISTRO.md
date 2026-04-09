# Exercício 03 — Registro de Resolução de Conflito

## O que causou o conflito

**Arquivo:** `projeto/hello-word.html`  
**Trecho:** linha 162 — o elemento `<div class="hint">` que exibe a dica do jogo.

Duas branches foram criadas a partir do mesmo commit em `main` (commit `19e5ea0`):

- **`feat/conflito-a`**: alterou o texto da dica para `"Professores da disciplina CIN0136 — CIn UFPE"`
- **`feat/conflito-b`**: alterou o mesmo texto para `"Dois nomes — um é Vinicius, o outro começa com K"`

O merge de `feat/conflito-a` em `main` foi feito primeiro (via Pull Request #2). Quando tentei fazer o merge de `feat/conflito-b`, o Git detectou que o mesmo trecho havia sido modificado de formas diferentes e não conseguiu resolver automaticamente.

## Marcadores de conflito encontrados

```
<<<<<<< HEAD
<div class="hint">Dica: <strong>Professores da disciplina CIN0136 — CIn UFPE</strong></div>
=======
<div class="hint">Dica: <strong>Dois nomes — um é Vinicius, o outro começa com K</strong></div>
>>>>>>> feat/conflito-b
```

- A seção entre `<<<<<<< HEAD` e `=======` era a versão já na `main` (vinda do `feat/conflito-a`).
- A seção entre `=======` e `>>>>>>> feat/conflito-b` era a versão da branch sendo mergeada.

## Como decidi qual versão manter

Optei por combinar as duas versões, mantendo tanto o contexto da disciplina (do `feat/conflito-a`) quanto a ideia de mencionar os dois professores (do `feat/conflito-b`):

```html
<div class="hint">Dica: <strong>Dois professores de CIN0136 — CIn UFPE</strong></div>
```

Essa versão é mais informativa do que a versão do `feat/conflito-b` (que era vaga demais) e mais interessante do que a versão do `feat/conflito-a` (que revelava apenas o contexto sem o número de professores).

## Como o conflito foi marcado como resolvido

1. Editei manualmente o arquivo `projeto/hello-word.html`, removendo os marcadores de conflito (`<<<<<<<`, `=======`, `>>>>>>>`) e deixando apenas a versão final escolhida.
2. Rodei `git add projeto/hello-word.html` para marcar o arquivo como resolvido no índice do Git.
3. Rodei `git commit` para completar o merge — o Git criou automaticamente o commit de merge.

## Estado do repositório após a resolução

```
git log --oneline -3
20a9027 fix(conflito): resolve conflito de merge entre feat/conflito-a e feat/conflito-b
5f832b1 style(hello-word): atualiza texto da dica do jogo
19e5ea0 feat(hello-word): adiciona um link para meu github
```
