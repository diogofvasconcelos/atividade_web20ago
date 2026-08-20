# 4. Usando o Git no seu computador

Agora vamos trazer o projeto para a sua máquina, editar com seus programas favoritos
(VS Code, Bloco de Notas, o que for) e mandar de volta para o GitHub.

Tudo aqui é feito no **Git Bash** (Windows) ou no **Terminal** (Mac/Linux).

---

## Antes: sobrevivendo à janela preta

Você só precisa de três comandos para se locomover:

```bash
pwd
```
Mostra em que pasta você está ("print working directory").

```bash
ls
```
Lista os arquivos da pasta atual.

```bash
cd Desktop
```
Entra na pasta `Desktop`. Para **voltar uma pasta**, use `cd ..`

Atalhos que salvam tempo:
- **Tab** completa o nome do arquivo/pasta automaticamente. Use sempre.
- **Seta para cima** repete o comando anterior.
- No Git Bash, colar é **Shift + Insert** ou botão direito → Paste (Ctrl+V às vezes não funciona).
- Caminhos no Git Bash usam `/` e não `\`: `cd /c/Users/SeuNome/Desktop`

> 💡 **Atalho preferido**: abra a pasta no Explorador de Arquivos, clique com o botão
> direito num espaço vazio e escolha **"Open Git Bash here"**. Ele já abre no lugar certo.

---

## Caminho A — Baixar um repositório que já existe (clone)

**Clonar** = fazer uma cópia completa do repositório do GitHub no seu computador.

1. No GitHub, abra o repositório e clique no botão verde **`< > Code`**.
2. Na aba **HTTPS**, copie o endereço (algo como
   `https://github.com/seu-username/meu-primeiro-repositorio.git`).
3. No Git Bash, vá para onde quer guardar o projeto:

```bash
cd ~/Desktop
```

4. Clone:

```bash
git clone https://github.com/seu-username/meu-primeiro-repositorio.git
```

Vai aparecer uma pasta nova com o nome do repositório. Entre nela:

```bash
cd meu-primeiro-repositorio
```

> Você só clona **uma vez** por projeto. Depois disso, usa `git pull` para atualizar.

---

## Caminho B — Enviar uma pasta que já está no seu computador

Já tem um projeto pronto e quer colocá-lo no GitHub? Faça assim:

1. Crie um repositório **vazio** no GitHub (desmarque "Add a README file").
2. Abra o Git Bash **dentro da pasta do projeto** e rode, na ordem:

```bash
git init
```
Transforma a pasta em um repositório Git (cria a pasta oculta `.git`).

```bash
git add .
```
Prepara **todos** os arquivos para o commit.

```bash
git commit -m "primeiro commit"
```
Tira a foto.

```bash
git branch -M main
```
Garante que a branch principal se chame `main`.

```bash
git remote add origin https://github.com/seu-username/nome-do-repo.git
```
Diz ao Git **para onde** enviar. `origin` é só um apelido para esse endereço.

```bash
git push -u origin main
```
Envia. O `-u` grava a ligação, então nas próximas vezes basta `git push`.

---

## O ciclo do dia a dia (o que você mais vai usar)

### 1. Ver a situação

```bash
git status
```

Esse é o comando mais importante do Git. Rode **antes e depois** de tudo.
Ele diz em português-ish o que está acontecendo e geralmente sugere o próximo comando.

Traduzindo o que ele mostra:
- **`Untracked files`** (vermelho): arquivos novos que o Git ainda não acompanha.
- **`Changes not staged for commit`** (vermelho): arquivos alterados, ainda não preparados.
- **`Changes to be committed`** (verde): já estão preparados, prontos para o commit.
- **`nothing to commit, working tree clean`**: tudo salvo e sincronizado. 👌

### 2. Editar os arquivos

Abra a pasta no editor de texto e trabalhe normalmente. O Git não atrapalha nada.

### 3. Preparar os arquivos (add)

```bash
git add .
```
O ponto significa "tudo que mudou nesta pasta". Para um arquivo específico:

```bash
git add index.html
```

> **Por que existe esse passo?** Porque nem sempre você quer commitar tudo de uma vez.
> Pense no `add` como colocar as pessoas na foto antes de bater a foto (`commit`).

### 4. Tirar a foto (commit)

```bash
git commit -m "adiciona a seção de contato na página inicial"
```

O texto entre aspas é a mensagem. Escreva bem — veja as dicas no
[arquivo 3](03-primeiro-repositorio-no-site.md#como-escrever-boas-mensagens-de-commit).

> Neste ponto a mudança está salva **no seu computador**. O GitHub ainda não sabe de nada.

### 5. Enviar para o GitHub (push)

```bash
git push
```

Atualize a página do repositório no navegador: sua mudança está lá. ✨

### 6. Baixar o que mudou (pull)

Antes de começar a trabalhar, **sempre**:

```bash
git pull
```

Isso traz o que outras pessoas (ou você, pelo site) alteraram. Pular esse passo é a
causa número um de dor de cabeça com Git.

---

## Resumo visual do ciclo

```
   ┌──────────────────────────────────────────────────────┐
   │                                                      │
   │   Seu computador                    GitHub (nuvem)   │
   │                                                      │
   │   [pasta do projeto]                [repositório]    │
   │          │                                 │         │
   │          │  git add + git commit           │         │
   │          ▼                                 │         │
   │   [commits locais]  ──── git push ───────► │         │
   │                     ◄─── git pull  ─────── │         │
   │                                                      │
   └──────────────────────────────────────────────────────┘
```

---

## Comandos para "espiar" sem medo

Nenhum destes altera nada — pode rodar à vontade:

```bash
git log --oneline
```
Lista os commits, um por linha, do mais novo para o mais antigo.
(Se a listagem "prender" a tela, aperte **`q`** para sair.)

```bash
git diff
```
Mostra linha a linha o que você alterou e ainda não commitou.

```bash
git remote -v
```
Mostra para qual endereço do GitHub este projeto está apontando.

---

## O arquivo `.gitignore`

Alguns arquivos **não** devem ir para o GitHub: senhas, pastas gigantes de dependências,
arquivos temporários do sistema. Crie um arquivo chamado `.gitignore` na raiz do projeto
listando o que ignorar:

```gitignore
# arquivos do sistema
Thumbs.db
desktop.ini
.DS_Store

# pastas de dependências
node_modules/

# arquivos com segredos
.env
senhas.txt
```

O Git passa a fingir que esses arquivos não existem. **Faça isso antes do primeiro commit** —
depois que um segredo entra no histórico, tirar dá muito trabalho.

---

## Exercício

1. Clone o repositório `sobre-mim` que você criou no arquivo 3.
2. Crie um arquivo `notas.txt` com uma frase qualquer.
3. Rode `git status` e leia com calma o que ele diz.
4. Faça `git add .`, rode `git status` de novo e compare (o arquivo ficou verde).
5. Faça o commit com uma mensagem decente e dê `git push`.
6. Confira no navegador se o arquivo apareceu.

Deu certo? Você já sabe o essencial. Agora o próximo nível:
[5. Branches e Pull Request](05-branches-e-pull-request.md).
