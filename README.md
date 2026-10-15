# 🧱 Mural da Turma · AMS 2026

Um mural na internet onde **cada aluno coloca o seu cartão**: nome, um emoji e uma frase sobre o que quer criar com tecnologia.

👉 **Veja o mural no ar:** https://medinagui.github.io/mural-ams-2026/

O mais legal é **como** o cartão chega lá. Você vai usar o mesmo caminho que programadores do mundo todo usam para colaborar em projetos de verdade:

1. Você **cria um arquivo** com o seu cartão.
2. Você **pede para juntar** o seu arquivo ao projeto (isso se chama *pull request*).
3. Um **robô** confere se está tudo certo e responde ✅ ou ❌.
4. O professor **revisa e aprova** (isso se chama *merge*).
5. O site **se atualiza sozinho** e o seu cartão aparece no mural. 🎉

---

## 📖 Mini dicionário

| Palavra | O que é | Comparando com… |
|---|---|---|
| **Repositório** (repo) | A pasta do projeto, guardada no GitHub, com todo o histórico | Uma pasta compartilhada que lembra de tudo |
| **Commit** | Salvar uma mudança, com uma mensagem dizendo o que mudou | Salvar o jogo (checkpoint) |
| **Fork** | A sua cópia do projeto, na sua conta | Tirar xerox do caderno de um colega pra escrever na sua cópia |
| **Pull request** (PR) | Pedido para juntar a sua mudança ao projeto original | Entregar o trabalho pro professor corrigir |
| **Merge** | Juntar de vez a mudança ao projeto | O professor colar o seu trabalho no mural da sala |
| **O robô** (GitHub Actions) | Um programa que roda sozinho a cada PR e confere as regras | O fiscal da prova que confere se você preencheu o nome |
| **GitHub Pages** | Serviço do GitHub que transforma o projeto em site | A vitrine da loja |

---

## ✍️ Como mandar o seu cartão (tudo pelo navegador)

> Você precisa estar **logado** no GitHub. Não tem conta? Crie em https://github.com/signup (é grátis).

**1. Abra a pasta de cartões**
Entre em https://github.com/Medinagui/mural-ams-2026/tree/main/cartoes

**2. Crie um arquivo novo**
Clique no botão **Add file** → **Create new file**.
Se aparecer um aviso dizendo que você precisa fazer um *fork*, clique em **Fork this repository**. (É o GitHub criando a sua cópia do projeto. Normal!)

**3. Dê nome ao arquivo**
No campo do nome, escreva o seu **primeiro nome**, em **letras minúsculas**, **sem acento** e terminando em **`.json`**:

```
ana.json        joao.json        maria-clara.json
```

Se já existir alguém com o seu nome, acrescente algo: `joao-2.json` ou `joao-p.json`.

**4. Escreva o seu cartão**
Copie o modelo abaixo, cole na área grande de texto e troque o que está entre aspas:

```json
{
  "nome": "Ana",
  "emoji": "🎮",
  "frase": "Com tecnologia eu quero criar jogos que ensinam matemática",
  "cor": "rosa"
}
```

⚠️ Mantenha as **aspas** `"` e as **vírgulas** no fim das linhas (menos na última linha antes do `}`).

**5. Salve (commit)**
Clique em **Commit changes…** (ou **Propose changes**). Na mensagem, escreva algo como `Cartão da Ana` e confirme.

**6. Abra o pull request**
O GitHub vai mostrar uma página comparando as mudanças. Clique em **Create pull request** e, na tela seguinte, em **Create pull request** de novo.

**7. Espere o robô 🤖**
Em alguns segundos, o robô comenta no seu pull request:

- ✅ **Tudo certo!** Agora é só esperar o professor aprovar.
- 🔧 **Quase lá!** O robô diz exatamente o que arrumar. Para consertar: aba **Files changed** → **três pontinhos (⋯)** do arquivo → **Edit file** → arrume → **Commit changes**. O robô confere de novo sozinho.

**8. Olhe para a TV 📺**
Quando o professor fizer o merge, em mais ou menos um minuto o seu cartão aparece no mural!

---

## 📏 Regras do cartão

| Campo | O que colocar | Regras |
|---|---|---|
| `nome` | Seu primeiro nome | Só o primeiro nome, **sem sobrenome**. Até 20 letras. Pode ter acento e hífen (`Ana-Clara`). |
| `emoji` | 1 emoji que tenha a sua cara | Exatamente **1** emoji. |
| `frase` | Complete: *"Com tecnologia eu quero criar…"* | Até **80 caracteres**. Sem links, telefone ou e-mail. Sem palavrão. |
| `cor` | A cor do seu cartão | Uma destas: 🟥 `vermelho` · 🟧 `laranja` · 🟨 `amarelo` · 🟩 `verde` · 🩵 `turquesa` · 🟦 `azul` · 🟪 `roxo` · 🩷 `rosa` |

E mais:

- Cada pessoa manda **1 cartão**, só dentro da pasta `cartoes/`.
- Não dá para mexer no cartão dos outros (o robô percebe 😄).

**Como achar um emoji?** No Windows, aperte a tecla **Windows + .** (ponto). No celular, use o teclado de emojis. Ou copie de https://emojipedia.org.

---

## 🔒 Privacidade

Este repositório e o site são **públicos**: qualquer pessoa na internet pode ver. Por isso, só o **primeiro nome**, nada de sobrenome, foto, telefone, e-mail ou endereço. O robô ajuda a conferir, mas a responsabilidade é de todo mundo.

---

## 🔍 Para os curiosos: o que tem aqui dentro?

```
cartoes/            ← os cartões, 1 arquivo por pessoa (é aqui que você mexe!)
site/               ← a página do mural (HTML, CSS e JavaScript)
robo/               ← o "cérebro" do robô, escrito em JavaScript (Node.js)
.github/workflows/  ← as instruções que dizem QUANDO o robô trabalha
```

- **`.github/workflows/robo.yml`**: quando alguém abre um pull request, o GitHub liga um computador na nuvem, roda o robô e mostra ✅ ou ❌. Isso é **CI** (*Integração Contínua*): conferir cada mudança antes de juntar.
- **`.github/workflows/publicar.yml`**: quando o professor faz o merge, o GitHub monta o site e coloca no ar. Isso é **CD** (*Entrega Contínua*): publicar sozinho, sem ninguém copiar arquivo na mão.

Quer ver o mural no seu computador? Com o [Node.js](https://nodejs.org) instalado, dentro desta pasta:

```bash
node robo/montar-site.js    # junta os cartões
node robo/servir.js         # abre em http://localhost:8080
node --test robo/regras.test.js   # roda os testes do robô
```

---

Aula ministrada por Guilherme Medina (Thompson Tecnologia) para a turma do AMS · Centro Paula Souza, em 23/10/2026.

