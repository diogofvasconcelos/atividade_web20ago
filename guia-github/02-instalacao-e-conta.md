# 2. Criando a conta e instalando os programas

Aqui você prepara o terreno. Faz uma vez só na vida (por computador).

---

## Parte A — Criar a conta no GitHub

1. Acesse **https://github.com** e clique em **Sign up** (Cadastrar).
2. Informe:
   - **E-mail**: use um que você acessa sempre (o de estudo ou pessoal).
   - **Senha**: forte, e guarde no seu gerenciador de senhas.
   - **Username**: é o seu nome público, aparece no endereço do seu perfil
     (`github.com/seu-username`). Escolha algo profissional — `joao-silva` é melhor
     que `joaozinho_gamer_2010`. Dá para trocar depois, mas quebra links antigos.
3. Confirme o e-mail que o GitHub enviar.
4. **Ative a verificação em duas etapas (2FA)** quando ele pedir. O GitHub exige isso.
   Use um app como Google Authenticator, Authy ou Microsoft Authenticator.
   **Guarde os códigos de recuperação em um lugar seguro** — sem eles, perder o celular
   significa perder a conta.

> A conta gratuita já permite repositórios públicos e privados sem limite. Não precisa pagar nada.

---

## Parte B — Instalar o Git (Windows)

1. Baixe em **https://git-scm.com/download/win** (o download começa sozinho).
2. Execute o instalador. **Pode clicar em "Next" em tudo** — as opções padrão estão boas.
   Duas telas que vale olhar:
   - *"Choosing the default editor"*: se você não conhece o Vim, escolha
     **"Use Visual Studio Code as Git's default editor"** ou o Notepad.
   - *"Adjusting the name of the initial branch"*: pode marcar
     **"Override... "** e deixar `main` (é o padrão do GitHub hoje).
3. Ao terminar, você ganha um programa novo chamado **Git Bash**. É uma janela preta
   onde você digita comandos. Não tenha medo dela.

### Conferindo se deu certo

Abra o **Git Bash** (procure no menu Iniciar) e digite:

```bash
git --version
```

Se aparecer algo como `git version 2.45.1`, está instalado. 🎉

---

## Parte C — Dizer ao Git quem é você

O Git assina cada commit com seu nome e e-mail. Configure uma vez:

```bash
git config --global user.name "Seu Nome Completo"
```

```bash
git config --global user.email "seu-email@exemplo.com"
```

> Use **o mesmo e-mail** cadastrado no GitHub. Assim seus commits aparecem ligados ao seu perfil.

Para conferir o que foi salvo:

```bash
git config --global --list
```

---

## Parte D — Como o GitHub vai saber que é você (autenticação)

Quando você for enviar arquivos (`push`), o GitHub pede identificação.
**A senha da conta não funciona mais** para isso. Você tem duas opções:

### Opção 1 (recomendada para iniciante): deixar o navegador resolver

O instalador do Windows já traz o **Git Credential Manager**. Na primeira vez que você
der `push`, uma janela vai abrir pedindo para entrar com sua conta do GitHub pelo navegador.
Entre, autorize, e pronto — ele guarda isso e nunca mais pergunta.

### Opção 2: Personal Access Token (token de acesso)

Se a janela não abrir, ou se você preferir:

1. No GitHub: foto do perfil → **Settings** → role até o fim → **Developer settings**
2. **Personal access tokens** → **Tokens (classic)** → **Generate new token (classic)**
3. Dê um nome (`meu-notebook`), escolha a validade e marque a caixa **`repo`**
4. Clique em **Generate token** e **copie o código que aparece**

> ⚠️ Esse código aparece **uma única vez**. Copie e guarde no gerenciador de senhas.
> Ele vale como uma senha: nunca coloque dentro de um arquivo do projeto, nunca mande por WhatsApp.

Quando o Git pedir `Username`, digite seu username. Quando pedir `Password`, **cole o token**.

---

## Parte E (opcional) — GitHub Desktop, para quem odeia digitar comandos

Se a janela preta te assusta, existe o **GitHub Desktop**: um programa com botões que faz
commit, push e pull no clique. Baixe em **https://desktop.github.com**.

É uma muleta perfeitamente válida para começar. Mas recomendo aprender os comandos do
arquivo 4 em algum momento: em entrevista, aula ou servidor, é o que vão te pedir.

---

## Checklist antes de seguir

- [ ] Conta criada e e-mail confirmado
- [ ] 2FA ativado e códigos de recuperação guardados
- [ ] `git --version` responde no Git Bash
- [ ] `git config --global --list` mostra seu nome e e-mail

Tudo marcado? Vá para [3. Seu primeiro repositório](03-primeiro-repositorio-no-site.md).
