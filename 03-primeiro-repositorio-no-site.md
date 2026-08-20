# 3. Seu primeiro repositório (sem instalar nada)

Antes de mexer em comandos, vamos fazer tudo pelo **navegador**. É o jeito mais fácil de
entender o que acontece. Ao final, você terá um projeto de verdade publicado na internet.

---

## Passo 1 — Criar o repositório

1. Entre em **https://github.com** já logado.
2. No canto superior direito, clique no **`+`** → **New repository**.
3. Preencha:

| Campo | O que colocar |
|-------|---------------|
| **Repository name** | `meu-primeiro-repositorio` (sem espaços; use hífens) |
| **Description** | "Repositório de testes para aprender GitHub" |
| **Public / Private** | **Public** se quiser mostrar no portfólio, **Private** se for só seu |
| **Add a README file** | ✅ **Marque esta caixa** |
| **Add .gitignore** | Deixe em "None" por enquanto |
| **License** | Deixe em "None" por enquanto |

4. Clique em **Create repository**.

Pronto: você tem um repositório. O endereço é `github.com/seu-username/meu-primeiro-repositorio`.

---

## Passo 2 — Entender o que é o README

Aquele arquivo `README.md` que apareceu é a **capa do projeto**. O GitHub mostra o conteúdo
dele automaticamente na página inicial do repositório. É onde você explica:

- o que o projeto faz
- como usar
- quem fez

O `.md` significa **Markdown**: um jeito simples de formatar texto. Os principais:

```markdown
# Título grande
## Subtítulo
**negrito** e *itálico*

- item de lista
- outro item

1. lista numerada
2. segundo item

[texto do link](https://exemplo.com)

`comando ou código no meio da frase`
```

---

## Passo 3 — Editar um arquivo pelo site

1. Na página do repositório, clique em **`README.md`**.
2. Clique no **ícone de lápis** (✏️) no canto superior direito do arquivo.
3. Escreva algo, por exemplo:

```markdown
# Meu primeiro repositório

Estou aprendendo a usar o GitHub. Este arquivo foi editado direto pelo navegador.

## O que já aprendi
- Criar um repositório
- Escrever em Markdown
- Fazer um commit
```

4. Clique em **Commit changes...** (botão verde).
5. Aparece uma caixinha pedindo a **mensagem do commit**. Escreva algo que explique
   a mudança: `atualiza o README com minhas anotações`.
6. Deixe marcado **"Commit directly to the main branch"** e clique em **Commit changes**.

**Parabéns, você acabou de fazer seu primeiro commit.** 🎉

---

## Passo 4 — Ver o histórico

1. Na página inicial do repositório, clique em **Commits** (ou no ícone de relógio, perto do topo).
2. Você vê a lista de tudo que já aconteceu, com autor, data e mensagem.
3. Clique em qualquer commit para ver **exatamente o que mudou**:
   - linhas em **verde** com `+` foram adicionadas
   - linhas em **vermelho** com `-` foram removidas

Isso é o superpoder do Git: nada se perde e tudo é rastreável.

---

## Passo 5 — Criar um arquivo novo

1. Página inicial do repositório → botão **Add file** → **Create new file**.
2. No campo do nome, digite `anotacoes.md`.
3. Escreva qualquer coisa no corpo.
4. Role até o fim e clique em **Commit changes**.

---

## Passo 6 — Enviar um arquivo do seu computador

1. **Add file** → **Upload files**.
2. Arraste um arquivo (uma imagem, um PDF, um `.html`).
3. Escreva a mensagem do commit e confirme.

> ⚠️ **Nunca envie**: senhas, tokens, chaves de API, documentos pessoais, ou arquivos
> muito grandes (acima de 100 MB o GitHub recusa). Se o repositório for público,
> qualquer pessoa do mundo vê o conteúdo — e o histórico guarda mesmo o que você apagar depois.

---

## Como escrever boas mensagens de commit

A mensagem explica **o que mudou e por quê**. Quem lê é você, daqui a 6 meses.

| ❌ Ruim | ✅ Bom |
|--------|-------|
| `alterações` | `corrige o alinhamento do menu no celular` |
| `asdasd` | `adiciona a página de contato` |
| `update` | `remove a imagem quebrada do rodapé` |
| `arrumei` | `atualiza o e-mail de contato no README` |

Dica de ouro: comece com um verbo no presente — *adiciona, corrige, remove, atualiza, ajusta*.

---

## Exercício

1. Crie um repositório chamado `sobre-mim`, público, com README.
2. Edite o README com: seu nome, o que você estuda e 3 coisas que quer aprender.
3. Crie um arquivo `metas.md` com suas metas do semestre.
4. Abra a aba de commits e confira se aparecem **3 commits** com mensagens claras.

Feito? Agora sim, vamos para o computador: [4. Usando no seu computador](04-usando-no-seu-computador.md).
