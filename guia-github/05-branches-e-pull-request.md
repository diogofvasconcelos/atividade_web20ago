# 5. Branches e Pull Requests (trabalhando sem quebrar nada)

Até aqui você mexeu direto na versão principal do projeto. Funciona quando você está
sozinho testando. Mas e quando o projeto já está no ar, ou tem outras pessoas nele?

---

## O que é uma branch

**Branch** significa "galho". É uma **linha de trabalho paralela**: uma cópia do projeto
onde você pode experimentar à vontade, sem afetar a versão principal.

```
                              ┌──── (branch: menu-novo) ──── commit ── commit ──┐
                              │                                                 ▼
main ── commit ── commit ─────┴─────────── commit ──────────────────────────── junção
                                                                            (merge)
```

- **`main`** (antigamente `master`) é a branch principal, a versão "boa" do projeto.
- Você cria uma branch para cada tarefa: `corrige-menu`, `pagina-contato`, `ajuste-cores`.
- Quando a tarefa fica pronta e testada, você **junta** (merge) na `main`.

Se der tudo errado na sua branch, basta apagá-la. A `main` continua intacta.

> Este repositório, por exemplo, tem uma branch chamada `qualidade` — criada justamente
> para trabalhar num assunto separado sem mexer na principal.

---

## Trabalhando com branches (comandos)

### Ver em qual branch você está

```bash
git branch
```
A branch atual aparece com um `*` na frente. (Aperte `q` se a lista prender a tela.)

### Criar uma branch e já mudar para ela

```bash
git switch -c minha-nova-branch
```

> Em versões antigas do Git o comando é `git checkout -b minha-nova-branch`.
> Os dois funcionam; `switch` é o mais novo e mais claro.

### Trocar de branch

```bash
git switch main
```

Repare: os arquivos na pasta **mudam sozinhos** quando você troca de branch.
Isso é normal — o Git está te mostrando a versão daquela linha de trabalho.

### Enviar sua branch nova para o GitHub

```bash
git push -u origin minha-nova-branch
```

### Juntar sua branch na main (merge local)

```bash
git switch main
```

```bash
git merge minha-nova-branch
```

### Apagar a branch depois que ela já foi juntada

```bash
git branch -d minha-nova-branch
```

---

## O que é um Pull Request (PR)

Um **Pull Request** é um pedido: *"terminei meu trabalho nesta branch, dá uma olhada e,
se estiver bom, junte na main"*.

É o coração do trabalho em equipe no GitHub. Ele oferece:
- uma tela mostrando **tudo o que mudou**, linha a linha
- espaço para **comentários e revisão** dos colegas
- um botão para **juntar** quando estiver aprovado

> Curiosidade: no GitLab isso se chama *Merge Request*. É a mesma coisa.

### Como abrir um Pull Request

1. Envie sua branch: `git push -u origin minha-branch`
2. Abra o repositório no GitHub. Vai aparecer uma faixa amarela:
   **"minha-branch had recent pushes"** → clique em **Compare & pull request**.
   (Se não aparecer: aba **Pull requests** → **New pull request**.)
3. Confira a linha do topo: `base: main` ← `compare: minha-branch`.
   Ela diz "quero jogar *minha-branch* dentro da *main*".
4. Escreva:
   - **Título**: resumo curto (`Adiciona página de contato`)
   - **Descrição**: o que mudou, por que, e como testar
5. Clique em **Create pull request**.
6. Role a página e clique em **Files changed** para revisar você mesmo antes de pedir revisão.

### Como juntar (merge) o PR

Quando estiver aprovado, clique em **Merge pull request** → **Confirm merge**.
Depois aparece o botão **Delete branch** — pode apagar sem medo, o histórico fica guardado.

E no seu computador, atualize a main:

```bash
git switch main
```

```bash
git pull
```

---

## Contribuindo no projeto de outra pessoa (fork)

Você não tem permissão de escrita no repositório de estranhos. O caminho é:

1. **Fork**: no repositório do outro, clique em **Fork** (canto superior direito).
   Isso cria uma **cópia sua** do projeto, na sua conta.
2. **Clone o seu fork** para o computador.
3. Crie uma branch, faça as alterações, commit e push.
4. Abra um **Pull Request** do seu fork para o repositório original.
5. O dono do projeto revisa e decide se aceita.

É exatamente assim que projetos de código aberto do mundo inteiro funcionam.

---

## Conflito de merge: o bicho-papão que não é tão feio

Acontece quando duas pessoas editam **a mesma linha do mesmo arquivo**. O Git não sabe
qual versão vale e pede sua ajuda. O arquivo fica assim:

```
<<<<<<< HEAD
<h1>Bem-vindo ao nosso site</h1>
=======
<h1>Bem-vinda ao nosso site</h1>
>>>>>>> minha-branch
```

Como resolver, em 4 passos:

1. Abra o arquivo no editor.
2. Decida qual versão fica (ou escreva uma nova misturando as duas).
3. **Apague as linhas de marcação** `<<<<<<<`, `=======` e `>>>>>>>`.
   O arquivo tem que ficar exatamente como você quer que fique.
4. Salve e finalize:

```bash
git add .
```

```bash
git commit -m "resolve conflito no titulo da pagina"
```

Se entrou em pânico e quer simplesmente cancelar o merge e voltar ao estado anterior:

```bash
git merge --abort
```

---

## Boas práticas de equipe

- **Uma branch por tarefa.** Nomes descritivos: `corrige-login`, não `teste2`.
- **`git pull` antes de começar** a trabalhar, sempre.
- **Commits pequenos e frequentes** valem mais que um commit gigante no fim do dia.
- **Nunca dê `push --force` na `main`.** Isso reescreve o histórico dos outros.
- **Não commite direto na `main`** em projeto compartilhado — use PR.

---

## Exercício

1. No seu repositório `sobre-mim`, crie a branch `nova-secao`.
2. Adicione uma seção "Hobbies" no README, faça commit e push.
3. Abra um Pull Request no GitHub e escreva uma descrição de verdade.
4. Revise em **Files changed**, faça o merge e apague a branch.
5. No computador: `git switch main` e `git pull` para receber a alteração.

Próximo: [6. Erros comuns e como resolver](06-erros-comuns.md).
