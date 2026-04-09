# Exercício 02 — Branches e Merges

## Objetivo

Praticar a criação de branches com propósitos distintos, trabalho paralelo e integração via Pull Request.

## Branches criadas

### `feat/sitesimples`
Branch criada para desenvolver a estrutura inicial do projeto HTML. Contém os primeiros commits com a página do Jogo da Forca.

### `feat/informacoes`
Branch criada para adicionar informações e documentação ao projeto:
- Adição do contexto do projeto na página
- Link para o GitHub do desenvolvedor
- Preenchimento do README e REFLEXAO

### `feat/conflito-a` e `feat/conflito-b`
Branches criadas especificamente para demonstrar a criação e resolução de um merge conflict (ver ex03-conflito).

## Fluxo de trabalho

```
main
 ├── feat/sitesimples  → merge via PR
 ├── feat/informacoes  → merge via PR
 ├── feat/conflito-a   → merge direto (para criar conflito)
 └── feat/conflito-b   → merge com conflito → resolução manual
```

## Naming convention usada

O padrão `tipo/descricao` foi seguido em todas as branches:

- `feat/` para novas funcionalidades
- `fix/` para correções
- `docs/` para documentação

## O que aprendi

Trabalhar com branches deixou claro que o `HEAD` é simplesmente um ponteiro que indica em qual commit estou trabalhando agora. Criar uma branch é apenas criar um novo ponteiro — o repositório não duplica arquivos. O que parecia complexo virou simples quando entendi isso.
