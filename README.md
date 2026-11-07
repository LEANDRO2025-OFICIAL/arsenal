# Arsenal

Coleção centralizada de skills, agents, MCP servers, hooks e configurações do Claude Code.

## Estrutura

```
arsenal/
├── skills/           # Skills externas clonadas + symlink para nativas
├── agents/           # 250+ agentes customizados
├── mcp-servers/      # Configurações MCP (mcp.json)
├── hooks/            # Hooks do Claude Code
└── docs/             # Documentação e configs globais (CLAUDE.md, RTK.md)
```

## Skills Instaladas

### Externas (clonadas do GitHub)
| Repositório | Descrição |
|---|---|
| **mattpocock/skills** | TDD, code review, domain modeling, prototyping, research |
| **obra/superpowers** | Framework de development agentico (brainstorming, debugging, planning) |
| **anthropics/skills** | Skills oficiais da Anthropic |
| **ComposioHQ/awesome-claude-skills** | Coleção comunitária de skills |
| **appssemble/awesome-skill-md** | Diretório de skills Markdown |
| **vivy-yi/awesome-skills** | Coleção de skills diversas |
| **linny006/awesome-agent-skills** | Agentes especializados |
| **skillsdirectory/awesome-ai-skills** | Skills de IA gerais |
| **addyosmani/agent-skills** | Design e desenvolvimento web |
| **VoltAgent/awesome-agent-skills** | Agentes multi-plataforma |

### Nativas (~/.claude/skills/)
- **caveman** — Modo de resposta concisa
- **ponytail** — Lazy developer mode
- **superpowers** — Brainstorming, systematic debugging, plans
- **ui-ux-pro-max** — Inteligência de design UI profissional
- **impeccable** — Catch AI slop before it ships
- **graphify** — Knowledge graph generation (`/graphify`)
- **motion-video** — Produção de vídeos motion graphics
- **remember** — Sistema de memória persistente
- **pr-review-toolkit** — Code review, test coverage, silent failure detection
- **ecc:** — Extended Code Commands (build fix, security scan, testing, etc.)

## Agents (250+)

Categorias principais:
- **Engenharia**: backend, frontend, DevOps, database, security, mobile, desktop
- **Design**: UI/UX, brand identity, visual storytelling, accessibility
- **Negócios**: strategy, finance, marketing, sales, customer success
- **Científico**: bioinformatics, data science, clinical decision support
- **China market**: WeChat, Douyin, Xiaohongshu, Bilibili, Weibo
- **GIS/Geoespacial**: ArcGIS, QGIS, spatial analysis, drone mapping
- **Game dev**: Unity, Unreal, Godot, technical art, level design

## MCP Servers Configurados

- **codebase-memory-mcp** — Indexação semântica do codebase
- **open-design** — Workspace de design colaborativo (OpenDesign Cloud / Local Codex)
- **plugin:desktop-commander** — Operações no filesystem e terminal
- **plugin:chrome-devtools-mcp** — Debug browser-side
- **plugin:playwright** — Testes E2E
- **neon** — Database Postgres serverless
- **context7** — Documentação atual de bibliotecas/APIs

## Hooks Ativos

- **CAVEMAN MODE** — Respostas concisas, sem filler
- **PONYTAIL MODE** — Mínimo código necessário, máxima completude
- **RTK (Rust Token Killer)** — Otimização de tokens em CLI
- **claude-mem** — Memória persistente entre sessões
- **ECC (Extended Code Commands)** — Code review, security scan, build fix

## Setup

```bash
# 1. Clonar repositório
git clone <repo-url> arsenal
cd arsenal

# 2. Linkar skills externas (já clonadas)
for skill in skills/*/; do
  ln -sf "$(pwd)/$skill" ~/.claude/skills/$(basename "$skill")
done

# 3. Copiar agents
cp -r agents/* ~/.claude/agents/

# 4. Copiar hooks
cp -r hooks/* ~/.claude/hooks/

# 5. Configurar MCP servers
cp mcp-servers/mcp.json ~/.claude/.mcp.json

# 6. Reiniciar Claude Code
```

## Manutenção

Para adicionar nova skill externa:
```bash
cd arsenal/skills
git clone --depth 1 <repo-url> <nome-skill>
```

Para atualizar todas as skills:
```bash
cd arsenal/skills
for dir in */; do
  cd "$dir" && git pull && cd ..
done
```

## Licenças

Cada skill mantém sua licença original. Verifique os repositórios fonte para detalhes.