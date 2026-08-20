# 7. Glossário — traduzindo o "GitHubês"

Consulte esta lista sempre que ouvir uma palavra estranha.

---

### Branch (*galho*)
Linha de trabalho paralela dentro do projeto. Permite experimentar sem afetar a versão
principal. A principal costuma se chamar `main`.

### Clone
Baixar uma cópia completa de um repositório do GitHub para o seu computador. Faz-se uma vez.

### Commit
Uma "foto" do projeto num momento, com autor, data e uma mensagem explicando a mudança.
É a unidade básica do histórico.

### Conflito (*merge conflict*)
Situação em que duas alterações mexeram na mesma linha e o Git não sabe qual manter.
Você decide manualmente. Ver [arquivo 5](05-branches-e-pull-request.md).

### Diff
A diferença entre duas versões: verde com `+` é o que foi adicionado, vermelho com `-` é
o que foi removido.

### Fork
Cópia do repositório de outra pessoa para dentro da sua conta, para você poder alterar
e depois propor as mudanças de volta.

### Git
O programa instalado no seu computador que controla as versões.

### GitHub
O site onde os repositórios ficam hospedados e compartilhados.

### GitHub Pages
Serviço gratuito do GitHub que publica um site (HTML/CSS/JS) direto do seu repositório,
com endereço `seu-username.github.io/nome-do-repo`. Ativa-se em **Settings → Pages**.

### `.gitignore`
Arquivo onde você lista o que o Git deve ignorar (senhas, pastas temporárias, `node_modules`).

### HEAD
Um apontador para "onde você está agora" no histórico. `HEAD~1` significa "um commit antes".

### Issue (*problema/tarefa*)
Um item na lista de tarefas do repositório: um bug para corrigir, uma ideia, uma dúvida.
Fica na aba **Issues**. Ótimo para organizar trabalho em grupo.

### Local × Remoto
**Local** é o que está no seu computador. **Remoto** é o que está no GitHub.
`push` e `pull` são as pontes entre os dois.

### `main` / `master`
Nome da branch principal. `master` era o padrão antigo; `main` é o padrão atual.
São só nomes — funcionam igual.

### Markdown (`.md`)
Linguagem simples de formatação usada nos READMEs. `# vira título`, `**vira negrito**`.

### Merge (*juntar*)
Unir as alterações de uma branch em outra.

### `origin`
Apelido padrão para o endereço do seu repositório no GitHub. Quando você digita
`git push origin main`, está dizendo "envie a branch main para o GitHub".

### Pull
Baixar do GitHub as alterações que você ainda não tem.

### Pull Request (PR)
Pedido formal para juntar sua branch na principal, com espaço para revisão e comentários.

### Push
Enviar seus commits do computador para o GitHub.

### README
Arquivo de apresentação do projeto, mostrado automaticamente na página inicial do repositório.

### Repositório (*repo*)
A pasta do projeto com todo o seu histórico. Pode ser local (computador) ou remota (GitHub).

### Staging area (*área de preparação*)
O lugar intermediário onde os arquivos ficam depois do `git add` e antes do `git commit`.
É o que permite escolher o que entra em cada commit.

### Star ⭐
Botão de "favoritar" um repositório no GitHub. Serve para salvar projetos interessantes
e para medir popularidade.

### Token (*Personal Access Token*)
Uma senha especial gerada pelo GitHub para autorizar o Git no seu computador.
Trate com o mesmo cuidado de uma senha.

### Working tree (*área de trabalho*)
Os arquivos como estão na sua pasta agora, incluindo as edições ainda não salvas no Git.

---

Última parada: [8. Cola rápida](08-cola-rapida.md).
