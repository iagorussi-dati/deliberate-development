# Deliberate Development

Um fluxo de desenvolvimento com agents de IA que te guia desde a ideia até o código testado. Inspirado no workflow do [Matt Pocock](https://www.youtube.com/watch?v=dy7SFVbh4-g).

## O que é isso?

É uma pasta `.kiro/` pronta pra usar. Dentro dela tem 6 agents de IA que trabalham em sequência:

| Atalho | Agent | O que faz |
|--------|-------|-----------|
| `ctrl+1` | **dd-grill** | Te entrevista sobre a sua ideia até vocês dois entenderem o que precisa ser feito |
| `ctrl+2` | **dd-grill-docs** | Mesma coisa, mas olha o código e atualiza a documentação do domínio |
| `ctrl+3` | **dd-prd** | Escreve um documento de requisitos (PRD) e publica como Issue no GitHub |
| `ctrl+4` | **dd-issues** | Quebra o PRD em tarefas pequenas e publica cada uma como Issue |
| `ctrl+5` | **dd-coder** | Implementa as tarefas com TDD (escreve teste primeiro, depois o código) |
| `ctrl+6` | **dd-qa** | Testa o que foi feito e reporta bugs como Issues |

## O fluxo

```
Ideia → dd-grill → dd-grill-docs → dd-prd → dd-issues → dd-coder → dd-qa
         ↑                                            |
         └────────── (encontrou bug? volta) ──────────┘
```

Você não precisa usar todos. Use o que fizer sentido. Mas a ordem é essa quando quer o fluxo completo.

## Como instalar

### Pré-requisitos

Você precisa ter instalado:

1. **Kiro CLI** — o próprio programa que roda os agents
2. **Node.js** (v18+) — pra rodar os MCP servers (playwright, context7)
3. **uv** — gerenciador de pacotes Python, usado pelo MCP server de git
4. **gh** (GitHub CLI) — pros agents que publicam Issues

### Instalando os pré-requisitos

```bash
# Node.js (se não tiver)
# No Ubuntu/Debian:
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs

# No Mac:
brew install node

# No Arch:
sudo pacman -S nodejs npm

# uv (gerenciador Python)
curl -LsSf https://astral.sh/uv/install.sh | sh

# GitHub CLI
# No Ubuntu/Debian:
sudo apt install gh

# No Mac:
brew install gh

# No Arch:
sudo pacman -S github-cli

# Depois de instalar o gh, faça login:
gh auth login
```

### Copiando pro seu projeto

```bash
# Clone este repositório (só precisa fazer uma vez)
git clone <URL_DESTE_REPO> ~/deliberate-development

# Copie a pasta .kiro pro seu projeto
cp -r ~/deliberate-development/.kiro /caminho/do/seu/projeto/

# Pronto! Agora entre no projeto e use o Kiro
cd /caminho/do/seu/projeto
kiro
```

## Como usar

### Começando um feature nova (fluxo completo)

1. Abra o terminal no seu projeto
2. Rode `kiro`
3. Aperte `ctrl+1` pra chamar o **grill**
4. Descreva sua ideia em português mesmo, pode ser informal
5. O agent vai te fazer perguntas. Responda até ele dizer que entendeu
6. Ele vai sugerir o próximo agent — siga o fluxo

### Só quer codar uma issue que já existe

1. `kiro`
2. `ctrl+5` (dd-coder)
3. Cola o número da issue: "implementa a #42"

### Quer testar o que foi feito

1. `kiro`
2. `ctrl+6` (qa)
3. Descreve o que tá errado ou pede pra ele explorar

## Personalizando

### Mudar o idioma

Cada arquivo em `.kiro/agents/prompts/` começa com `Responda em pt-BR.` — mude pra `Respond in English.` se preferir.

### Mudar o modelo

Cada arquivo `.json` em `.kiro/agents/` tem um campo `"model"`. Mude pra qualquer modelo suportado pelo Kiro (ex: `"claude-sonnet-4-20250514"`).

### Adicionar/remover MCP servers

Os MCP servers ficam no campo `"mcpServers"` de cada agent JSON. Se você não usa Playwright, pode remover o bloco inteiro sem problema.

### Adicionar steering (instruções globais)

Crie `.kiro/steering/` com arquivos `.md` pra dar contexto pros agents sobre seu ambiente. Exemplo:

```markdown
# Ambiente

- Usamos pnpm, não npm
- Deploy é feito via Vercel
- Banco de dados: Supabase (Postgres)
```

## Créditos

Fluxo baseado no [Agentic Development workflow do Matt Pocock](https://www.youtube.com/watch?v=dy7SFVbh4-g). Adaptado e configurado para o Kiro CLI.
