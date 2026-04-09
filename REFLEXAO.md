# Reflexão — EI1 Portfólio Git

**Disciplina:** CIN0136 — Desenvolvimento de Software  
**Aluno:** Caio Agrelli  
**Período:** 2026.1

---

## O que foi difícil

A parte mais complicada para mim foi entender o estado do repositório durante e depois de um merge conflict. Eu sabia que tinha um conflito, conseguia ver os marcadores `<<<<<<<`, `=======` e `>>>>>>>` no arquivo, mas não entendia completamente o que o Git estava esperando de mim naquele momento. O repositório ficava num estado intermediário que eu não sabia nomear — não estava num commit, não estava limpo, e qualquer comando que eu tentava dava um erro dizendo que o merge estava pendente.

Outro ponto que travou foi entender a diferença entre `git merge` e o que acontece quando você faz um merge via Pull Request no GitHub. Localmente, eu estava acostumado a fazer tudo pela linha de comando, então quando precisei abrir um PR e fazer o merge pela interface, tive que entender que o resultado no histórico seria diferente dependendo de como eu fizesse — fast-forward, merge commit ou squash. Não sabia que existiam essas três opções até precisar escolher uma.

A nomenclatura de branches também foi um ponto de atenção. No início, eu criava branches com nomes genéricos como `branch1` ou `teste`, o que tornava impossível entender o histórico depois. Adotar o padrão `tipo/descricao` exigiu pensar antes de criar, o que é um hábito diferente.

---

## O que ficou claro

O que ficou mais claro foi a ideia de que **uma branch é apenas um ponteiro para um commit**. Antes, eu imaginava que criar uma branch copiava arquivos ou criava algum estado pesado no repositório. Quando entendi que é só um label apontando para um hash, tudo fez mais sentido: por que branches são baratas de criar, por que o checkout é instantâneo, por que o Git consegue gerenciar tantas branches ao mesmo tempo sem custo.

Também ficou claro o propósito dos commits semânticos. Ao ler o histórico do próprio repositório, percebi que os commits com tipo e escopo descritos (`feat(hello-word): adiciona pagina da forca`) contam uma história coerente, enquanto um commit vago não diz nada. Isso não é burocracia — é comunicação.

A relação entre `HEAD`, a branch atual e o commit apontado também clicou. Quando você faz `git checkout outra-branch`, o `HEAD` passa a apontar para a outra branch, que por sua vez aponta para o commit mais recente dela. O working directory muda pra refletir isso. É simples assim — e entender isso tornou muito menos misterioso o que acontece quando você troca de branch ou faz um detached HEAD por acidente.

---

## O que ainda é confuso

O que ainda não ficou completamente claro para mim é a estratégia de rebase versus merge. Eu sei que `git rebase` reescreve o histórico de commits para que eles apareçam como se tivessem sido feitos em cima da branch alvo, enquanto `git merge` cria um commit de merge que preserva os dois históricos. Mas não sei intuitivamente quando usar um ou outro em um time real. Li que o rebase é "mais limpo" mas "perigoso em branches compartilhadas" — só que ainda não consegui internalizar exatamente qual é o perigo e por quê.

Também ainda tenho dúvida sobre como funciona o `git stash` na prática em cenários mais complexos. Eu usei uma vez para guardar mudanças temporariamente antes de trocar de branch, funcionou, mas não sei o que aconteceria se eu fizesse `stash` em várias situações diferentes e depois tentasse aplicar seletivamente.

Por fim, ainda não entendo completamente como funciona o histórico quando você tem branches que divergiram por muito tempo e depois são mergeadas. O grafo fica complexo e fica difícil de ler o que aconteceu em qual ordem. Vou precisar praticar mais com `git log --graph` para desenvolver essa leitura.

---

*Este documento foi escrito com honestidade sobre o processo de aprendizagem. Git é uma ferramenta que se aprende fazendo — e fazendo errado algumas vezes.*
