# 8. Cola rápida (imprima ou deixe aberta)

Uma página só. Se você decorar apenas o bloco "os 4 de todo dia", já dá para trabalhar.

---

## ⭐ Os 4 de todo dia

```bash
git pull
```
```bash
git add .
```
```bash
git commit -m "descrição do que mudou"
```
```bash
git push
```

E, na dúvida sobre qualquer coisa:

```bash
git status
```

---

## Configuração inicial (uma vez por computador)

| Comando | O que faz |
|---------|-----------|
| `git config --global user.name "Seu Nome"` | Define seu nome nos commits |
| `git config --global user.email "email@exemplo.com"` | Define seu e-mail |
| `git config --global init.defaultBranch main` | Novos repositórios já nascem com `main` |
| `git config --global pull.rebase false` | Define merge como padrão do `pull` |
| `git config --global --list` | Mostra tudo que está configurado |

---

## Começar um projeto

| Comando | O que faz |
|---------|-----------|
| `git clone <url>` | Baixa um repositório do GitHub |
| `git init` | Transforma a pasta atual em repositório |
| `git remote add origin <url>` | Liga a pasta local a um repositório no GitHub |
| `git remote -v` | Mostra a qual repositório remoto está ligado |
| `git push -u origin main` | Primeiro envio (grava a ligação) |

---

## Dia a dia

| Comando | O que faz |
|---------|-----------|
| `git status` | Mostra a situação atual |
| `git add .` | Prepara todos os arquivos alterados |
| `git add arquivo.txt` | Prepara apenas um arquivo |
| `git commit -m "msg"` | Salva a versão com uma mensagem |
| `git push` | Envia para o GitHub |
| `git pull` | Traz do GitHub |

---

## Olhar o histórico (não altera nada)

| Comando | O que faz |
|---------|-----------|
| `git log --oneline` | Lista os commits, um por linha |
| `git log --oneline --graph --all` | Histórico em forma de desenho, com as branches |
| `git diff` | Mostra o que mudou e ainda não foi preparado |
| `git diff --staged` | Mostra o que já foi preparado com `add` |
| `git show <hash>` | Mostra tudo de um commit específico |

> Preso na listagem? Aperte **`q`**.

---

## Branches

| Comando | O que faz |
|---------|-----------|
| `git branch` | Lista as branches (a atual tem `*`) |
| `git switch -c nome` | Cria uma branch e muda para ela |
| `git switch nome` | Troca para uma branch existente |
| `git merge nome` | Junta a branch `nome` na atual |
| `git push -u origin nome` | Envia a branch nova para o GitHub |
| `git branch -d nome` | Apaga a branch (após o merge) |

---

## Desfazer

| Comando | O que faz |
|---------|-----------|
| `git restore arquivo` | Descarta as alterações não commitadas do arquivo |
| `git restore --staged arquivo` | Tira o arquivo da preparação (desfaz o `add`) |
| `git commit --amend -m "msg"` | Corrige a mensagem do último commit |
| `git reset --soft HEAD~1` | Desfaz o último commit, mantendo os arquivos |
| `git merge --abort` | Cancela um merge que deu conflito |

---

## Markdown essencial (para o README)

```markdown
# Título 1
## Título 2
### Título 3

**negrito**   *itálico*   ~~riscado~~

- lista
- de itens

1. lista
2. numerada

[link](https://exemplo.com)
![imagem](caminho/da/imagem.png)

`código na linha`

| Coluna A | Coluna B |
|----------|----------|
| dado 1   | dado 2   |

> citação

- [ ] tarefa pendente
- [x] tarefa concluída
```

---

## Navegação no Git Bash

| Comando | O que faz |
|---------|-----------|
| `pwd` | Mostra a pasta atual |
| `ls` | Lista os arquivos |
| `cd pasta` | Entra na pasta |
| `cd ..` | Volta uma pasta |
| `clear` | Limpa a tela |

**Tab** completa nomes · **Seta ↑** repete o comando anterior · **Shift+Insert** cola

---

## Quando tudo der errado

1. `git status` e leia a mensagem.
2. Procure o erro no [arquivo 6](06-erros-comuns.md).
3. Copie a pasta como backup, clone o repositório de novo e recomece.
