# 1. O que é Git e o que é GitHub

## A analogia do trabalho escolar

Imagine que você está escrevendo um trabalho no computador. É comum acabar com isso:

```
trabalho.docx
trabalho_final.docx
trabalho_final2.docx
trabalho_final_AGORA_VAI.docx
trabalho_final_versao_do_professor.docx
```

Um mês depois, ninguém sabe qual é o certo. E se duas pessoas editarem ao mesmo tempo,
alguém vai perder trabalho.

**O Git resolve exatamente isso.** Ele guarda todas as versões do seu projeto, com data,
autor e uma descrição do que mudou — tudo dentro de um único arquivo de projeto.

## Git ≠ GitHub

Muita gente confunde. São duas coisas diferentes:

| | **Git** | **GitHub** |
|---|---------|------------|
| O que é | Um **programa** que roda no seu computador | Um **site** na internet |
| Para que serve | Guardar o histórico das versões | Guardar seu projeto na nuvem e compartilhar |
| Precisa de internet? | Não | Sim |
| Analogia | O botão "salvar versão" | O Google Drive dos programadores |

Resumindo:
> **Git** é a ferramenta. **GitHub** é o lugar onde você coloca o resultado para os outros verem.

Existem concorrentes do GitHub (GitLab, Bitbucket), mas todos usam o mesmo Git por baixo.

## As 4 palavras que você precisa entender hoje

### 1. Repositório (ou "repo")
É a **pasta do seu projeto** sendo vigiada pelo Git. Tudo o que estiver dentro dela
passa a ter histórico. No GitHub, cada projeto é um repositório.

### 2. Commit
É uma **foto do projeto naquele momento**, com um bilhete explicando o que mudou.
Exemplo de bilhete: `"adiciona a tabela de preços na página inicial"`.

Cada commit fica salvo para sempre. Você pode voltar para qualquer um deles no futuro.

### 3. Push
É **enviar** seus commits do computador para o GitHub (subir).

### 4. Pull
É **trazer** para o computador o que mudou no GitHub (baixar).
Usado quando outra pessoa alterou o projeto, ou quando você editou pelo site.

## O ciclo do dia a dia

Depois de tudo configurado, 90% do seu uso vai ser este ciclo:

```
   1. pull        2. editar       3. add + commit     4. push
 (baixar o que  →  (mexer nos   →   (tirar a foto  →  (enviar para
  já mudou)         arquivos)        e descrever)      o GitHub)
```

E repete. Só isso. O resto do guia é detalhe.

## Por que isso importa mesmo para quem não programa

- **Histórico**: dá para ver quem mudou o quê, quando e por quê.
- **Segurança**: seu projeto fica salvo na nuvem, não só no computador que pode queimar.
- **Trabalho em equipe**: duas pessoas mexem no mesmo projeto sem sobrescrever a outra.
- **Portfólio**: no mercado de tecnologia, seu perfil do GitHub vale tanto quanto o currículo.

## Exercício

Antes de ir para o próximo arquivo, responda em voz alta (sem consultar):

1. Git roda no meu computador ou na internet?
2. O que é um commit?
3. `push` sobe ou baixa?

Se acertou as três, siga para [2. Instalação e conta](02-instalacao-e-conta.md).
