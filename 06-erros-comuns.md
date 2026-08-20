# 6. Erros comuns e como resolver

Mensagem vermelha no terminal **não** é o fim do mundo. Na maioria das vezes o próprio Git
já diz o que fazer. Abaixo estão os erros que 99% dos iniciantes encontram.

> 🔎 **Regra geral**: quando algo der errado, rode `git status` e leia a saída com calma.
> Ela quase sempre contém a solução.

---

## 1. `fatal: not a git repository`

```
fatal: not a git repository (or any of the parent directories): .git
```

**Significa:** você está numa pasta que o Git não acompanha.

**Solução:** confira onde você está com `pwd` e entre na pasta certa com `cd`.
Se realmente quer transformar essa pasta em repositório, use `git init`.

---

## 2. `Please tell me who you are`

**Significa:** você nunca configurou seu nome e e-mail.

**Solução:**

```bash
git config --global user.name "Seu Nome"
```

```bash
git config --global user.email "seu-email@exemplo.com"
```

Depois refaça o commit.

---

## 3. `Updates were rejected because the remote contains work...`

```
! [rejected] main -> main (fetch first)
```

**Significa:** o GitHub tem algo que você não tem no computador (você editou pelo site,
ou um colega enviou algo).

**Solução:** traga o que falta e envie de novo:

```bash
git pull
```

```bash
git push
```

> ⚠️ **Não** resolva isso com `git push --force`. Isso apaga o trabalho de outra pessoa.

---

## 4. `Authentication failed` ou erro 403

**Significa:** o GitHub não reconheceu você. Lembre: a **senha da conta não funciona** aqui.

**Solução:** use o token de acesso ou o login pelo navegador — está tudo explicado na
[Parte D do arquivo 2](02-instalacao-e-conta.md#parte-d--como-o-github-vai-saber-que-é-você-autenticação).

Se o Windows guardou uma credencial errada:
**Painel de Controle → Contas de Usuário → Gerenciador de Credenciais →
Credenciais do Windows** → apague a entrada `git:https://github.com` e tente de novo.

---

## 5. Abriu uma tela estranha e não consigo sair (o Vim)

Acontece quando você roda `git commit` **sem** o `-m "mensagem"`.
O Git abre um editor de texto dentro do terminal.

**Para sair salvando:** aperte `Esc`, digite `:wq` e aperte `Enter`.
**Para sair cancelando:** aperte `Esc`, digite `:q!` e aperte `Enter`.

**Para nunca mais passar por isso:** use sempre `git commit -m "sua mensagem"`.

---

## 6. A listagem "travou" e não volta ao normal

Comandos como `git log` e `git branch` abrem um visualizador de páginas.
Aperte **`q`** para sair. (Setas ou `Espaço` rolam o conteúdo.)

---

## 7. `error: src refspec main does not match any`

**Significa:** você tentou dar push numa branch que ainda não existe — geralmente porque
**você ainda não fez nenhum commit**.

**Solução:**

```bash
git add .
```

```bash
git commit -m "primeiro commit"
```

```bash
git push -u origin main
```

---

## 8. Commitei um arquivo que não devia (senha, arquivo enorme)

**Se ainda NÃO deu push:**

```bash
git rm --cached nome-do-arquivo
```

Adicione o arquivo ao `.gitignore` e faça um novo commit.

**Se JÁ deu push e era um segredo (senha, token, chave):**
o arquivo continua no histórico mesmo se você apagar. Considere-o **vazado**:

1. **Troque/revogue a senha ou token imediatamente.** Este passo é o que realmente importa.
2. Depois, se necessário, procure ajuda para limpar o histórico
   (é uma operação delicada, feita com `git filter-repo` ou o BFG).

---

## 9. Quero desfazer o último commit (ainda não dei push)

**Desfazer o commit mas manter as alterações nos arquivos:**

```bash
git reset --soft HEAD~1
```

**Só quer corrigir a mensagem do último commit:**

```bash
git commit --amend -m "mensagem corrigida"
```

> Não use `--amend` em commits que já foram enviados com push num projeto compartilhado.

---

## 10. Estraguei um arquivo e quero a versão anterior de volta

**Descartar alterações não commitadas de um arquivo:**

```bash
git restore nome-do-arquivo.html
```

**Descartar alterações de TUDO (⚠️ perde o trabalho não commitado, sem volta):**

```bash
git restore .
```

Pense duas vezes antes de rodar o de cima. O Git não consegue recuperar o que nunca foi commitado.

---

## 11. `You have divergent branches`

Aparece no `git pull` quando o Git não sabe como juntar as duas linhas. Defina o
comportamento padrão (fazer merge) uma vez só:

```bash
git config --global pull.rebase false
```

E rode `git pull` de novo.

---

## 12. `Your branch is ahead of 'origin/main' by 3 commits`

**Não é erro!** É só o Git avisando que você tem 3 commits salvos no computador que ainda
não foram enviados.

**Solução:** `git push`.

---

## 13. Fiz push mas não aparece nada no GitHub

Cheque três coisas:

1. Você está olhando a **branch certa** no site? Há um seletor de branch no topo da página.
2. O push foi para o repositório certo?

```bash
git remote -v
```

3. O commit foi realmente criado?

```bash
git log --oneline
```

---

## 14. `HEAD detached at ...`

**Significa:** você entrou no "modo visita" a um commit antigo, fora de qualquer branch.

**Solução:** volte para a sua branch:

```bash
git switch main
```

---

## Comandos que exigem cuidado

| Comando | O que faz | Cuidado |
|---------|-----------|---------|
| `git reset --hard` | Apaga alterações não commitadas | Sem volta |
| `git push --force` | Sobrescreve o histórico no GitHub | Pode apagar trabalho da equipe |
| `git clean -fd` | Deleta arquivos não rastreados | Sem volta |
| `git branch -D` | Apaga branch mesmo sem merge | Pode perder commits |

Se algum tutorial da internet mandar rodar um desses, entenda o que ele faz antes de colar.

---

## Quando nada funciona: o plano B honesto

1. **Copie a pasta do projeto inteira** para outro lugar (backup manual).
2. Clone o repositório de novo, limpo, do GitHub.
3. Copie manualmente os arquivos que você alterou para a cópia nova.
4. Commit e push.

Deselegante? Sim. Funciona? Sempre. Não tenha vergonha de usar.

---

Próximo: [7. Glossário](07-glossario.md).
