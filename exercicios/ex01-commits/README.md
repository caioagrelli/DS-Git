# Exercício 01 — Commits Semânticos

## Objetivo

Praticar o uso de commits seguindo o padrão [Conventional Commits](https://www.conventionalcommits.org/), garantindo que cada commit comunique claramente a intenção da mudança.

## Padrão utilizado

```
<tipo>(<escopo>): <descrição curta>
```

### Tipos válidos

| Tipo       | Quando usar                                     |
|------------|--------------------------------------------------|
| `feat`     | Nova funcionalidade ou arquivo                   |
| `fix`      | Correção de erro                                 |
| `docs`     | Alteração em documentação                        |
| `style`    | Mudança de estilo sem alterar comportamento      |
| `refactor` | Melhoria de código sem mudar comportamento       |
| `test`     | Adição ou modificação de testes                  |
| `chore`    | Configuração, dependências, arquivos auxiliares  |

## Commits realizados neste repositório

Abaixo estão os commits semânticos criados ao longo do projeto:

| Hash    | Mensagem                                              |
|---------|-------------------------------------------------------|
| 205b8fc | `feat: estrutura inicial do projeto`                  |
| 42af8d3 | `feat(hello-word): adiciona pagina da forca`          |
| f4e1108 | `feat(style): opçao de mudar de tema claro para escuro` |
| 8df1fbb | `style(hello-word): especificação da dica`            |
| 6e54f9f | `style(hello-word): especificação da dica`            |
| 19e5ea0 | `feat(hello-word): adiciona um link para meu github`  |
| 36e10a7 | `docs(hello-word): adiciona o contexto do projeto no site` |

## O que aprendi

O principal aprendizado foi entender que uma mensagem de commit é uma forma de comunicação — não só para o time, mas para o "eu do futuro" que vai ler o histórico e precisar entender o que foi feito e por quê. Commits genéricos como "atualização" ou "ok" são inúteis nesse contexto.
