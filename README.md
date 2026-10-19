# AgentQA Studio — download

Instaladores do **AgentQA Studio**, o app de QA com assistente de IA.
Este repositório tem **só os instaladores**: o código-fonte fica em repositório privado.

## ⬇️ Baixar

Página da versão mais nova: **[Releases → Latest](../../releases/latest)**

| Seu computador | Arquivo |
|---|---|
| Mac com chip Apple (M1, M2, M3, M4) | `AgentQA-Studio-<versão>-mac-arm64.dmg` |
| Mac com processador Intel | `AgentQA-Studio-<versão>-mac-x64.dmg` |
| Windows 10/11 | `AgentQA-Studio-<versão>-instalador.exe` |

Não sabe qual é o seu Mac? Menu  → **Sobre este Mac**. Se aparecer **Chip Apple M…**, é o `arm64`. Se aparecer **Processador Intel**, é o `x64`.

---

## 🍎 Instalar no Mac

1. Abra o `.dmg` e arraste **AgentQA Studio** para **Aplicativos**.
2. Abra o app. Na primeira vez o macOS avisa que **não pode verificar o desenvolvedor**: o app não tem a assinatura paga da Apple.
   Feche o aviso e vá em **Ajustes do Sistema → Privacidade e Segurança**. No fim da página, clique em **"Abrir Mesmo Assim"** e digite a senha do Mac.
   No macOS 14 ou anterior também funciona clicar com o **botão direito** no app → **Abrir** → **Abrir**.
3. Se aparecer **"está danificado e não pode ser aberto"**, é a quarentena do download. Rode no Terminal:
   ```bash
   xattr -dr com.apple.quarantine "/Applications/AgentQA Studio.app"
   ```

**O que o Mac precisa:** o app confere tudo em **Início → Primeiros passos → Computador pronto** e mostra o comando que falta.

| Item | Como instalar |
|---|---|
| Git e Python 3 | `xcode-select --install` |
| Claude Code | `curl -fsSL https://claude.ai/install.sh \| bash` e depois rode `claude` uma vez para entrar |
| Node.js 22 (navegador do assistente) | [nodejs.org](https://nodejs.org) ou `brew install node` |

## 🪟 Instalar no Windows

1. Rode o `AgentQA-Studio-<versão>-instalador.exe`.
2. Se aparecer **"O Windows protegeu o computador"** (o instalador não tem certificado pago), clique em **Mais informações** → **Executar assim mesmo**.
3. A instalação é por usuário: não pede administrador. O atalho fica na Área de Trabalho e no Menu Iniciar.

**O que o Windows precisa:** **WSL** (Ubuntu) com o **Claude Code** instalado e logado, além de **Git** e **Node.js 22** dentro do Ubuntu.
O app confere tudo em **Início → Primeiros passos → Computador pronto**.

## 🚀 Primeiro projeto

No menu do projeto (canto superior esquerdo): **Novo projeto de QA** → cole o endereço do kit de QA do time → escolha a pasta.
O app faz `git clone` do kit e abre o projeto.

## 🔄 Atualizar

Baixe o instalador da versão nova e instale por cima. Configurações, projetos e senhas salvas continuam.

## 🔒 Privacidade

- As senhas de teste ficam cifradas no computador de cada QA (Keychain no Mac, cofre do Windows) e nunca saem dele.
- O app não envia métricas nem dados de uso.
- O assistente trabalha só em ambientes de QA, nunca em produção.

## Conferir o arquivo (opcional)

Cada versão traz um `SHA256SUMS.txt`. No Mac: `shasum -a 256 AgentQA-Studio-*.dmg`. No Windows: `Get-FileHash .\AgentQA-Studio-*.exe`.
