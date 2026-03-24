# README - Governance Manifesto Template

Template reutilizável de governança de desenvolvimento assistido por IA. Contém manifesto, memória institucional, memória de sessão por sprint, planos de execução e templates de sprint.

## O que é este repositório?

Este é um **template de governança** que padroniza como sprints, memórias e planos são estruturados em projetos que usam agentes IA para desenvolvimento.

Contém:

- ✅ **Manifesto** de governança obrigatória
- ✅ **Templates** de sprints e memória
- ✅ **Planos de execução** reutilizáveis
- ✅ **Guias de instalação** passo-a-passo
- ✅ **Exemplos de uso** real

## Estrutura

```
neural-flow-framework/
├── docs/
│   ├── MANIFESTO-DEV-IA.md        # Regras obrigatorias
│   ├── MEMORY.md                  # Template de memoria inicial
│   └── SPRINTS-MVP.md             # Template de primeira sprint
├── .github/prompts/
│   └── plan-setup-governanca.prompt.md  # Plano de setup adaptavel
├── templates/
│   ├── SPRINTS-CHECKLIST-TEMPLATE.md # Template de indice de sprints
│   ├── sprint-template.md             # Template de sprint individual
│   └── memoria-sessao-sprint-template.md # Template de memoria de sessao por sprint
├── README.md                      # Este arquivo
├── INSTALL.md                     # Guia de instalacao
├── CHANGELOG.md                   # Historico do manifesto
├── LICENSE                        # Licenca MIT
└── FAQ.md                         # Perguntas frequentes
```

## Início Rápido

### 1. Copiar para seu projeto

```bash
# Clonar ou copiar esta estrutura
git clone https://github.com/seu-user/governance-manifesto-template.git
cd governance-manifesto-template

# Copiar para seu projeto
cp -r docs/ /seu-projeto/
cp -r .github/ /seu-projeto/
cp -r templates/ /seu-projeto/docs/
```

### 2. Adaptar ao seu contexto

```bash
cd /seu-projeto

# Editar MEMORY.md com estado inicial
nano docs/MEMORY.md

# Editar plan-setup-governanca.prompt.md
nano .github/prompts/plan-setup-governanca.prompt.md

# Criar SPRINTS-CHECKLIST.md para cada app
cp docs/templates/SPRINTS-CHECKLIST-TEMPLATE.md apps/seu-app/SPRINTS-CHECKLIST.md

# Criar pasta e memoria de sessao inicial da sprint
mkdir -p docs/sessoes/sprints
cp docs/templates/memoria-sessao-sprint-template.md docs/sessoes/sprints/sprint-1-seu-app-YYYY-MM-DD.md
```

### 3. Primeiro commit

```bash
git add docs/ .github/ apps/*/SPRINTS-CHECKLIST.md
git commit -m "docs(governança): inicia setup de manifesto"
git push origin main
```

## Como Usar

### Criar uma nova sprint

1. Criar arquivo: `apps/<app>/sprints/sprint-N.md` usando `docs/templates/sprint-template.md`
2. Preencher **snapshot operacional** (status, datas, próxima ação)
3. Definir checklist numerado com dependências claras
4. Atualizar `apps/<app>/SPRINTS-CHECKLIST.md` com referência
5. Executar ações técnicas **depois** de documentar a sprint
6. Criar/atualizar arquivo de memoria de sessao em `docs/sessoes/sprints/`
7. Registrar evidências de cada ação concluída

### Atualizar MEMORY.md

- No fim de cada sprint ou mudança estrutural
- Registrar estado atual do projeto, pendências e decisões
- Nunca incluir segredos ou dados sensíveis
- Manter curto (máx 200 linhas) para economia de contexto
- Tratar `MEMORY.md` como memória institucional e usar memória de sessão por sprint para o delta de execução

### Executar planos

1. Ler `.github/prompts/plan-setup-governanca.prompt.md`
2. Adaptar ao seu projeto (substituir placeholders `<...>`)
3. Seguir fases na ordem, marcando com `[x]` cada concluída
4. Confirmar critérios de verificação antes de passar à próxima

## Arquivos Principais

| Arquivo                                           | Papel                                   | Quando usar                                |
| ------------------------------------------------- | --------------------------------------- | ------------------------------------------ |
| `docs/MANIFESTO-DEV-IA.md`                        | Regras mandatórias de governança        | Primeira vez, referência contínua          |
| `docs/MEMORY.md`                                  | Memória institucional do projeto        | Iniciar sessão/sprint                      |
| `templates/memoria-sessao-sprint-template.md`     | Template da memória de sessão da sprint | Executar e registrar cada sessão de sprint |
| `docs/SPRINTS-MVP.md`                             | Exemplo de primeira sprint              | Criar sprint-1                             |
| `.github/prompts/plan-setup-governanca.prompt.md` | Plano adaptável de setup                | Setup inicial de novo projeto              |
| `templates/SPRINTS-CHECKLIST-TEMPLATE.md`         | Índice de sprints por app               | Criar SPRINTS-CHECKLIST.md                 |
| `templates/sprint-template.md`                    | Template de sprint detalhada            | Criar sprint-N.md                          |

## Estrutura Recomendada no seu Projeto

Após copiar, sua estrutura deve ficar assim:

```
seu-projeto/
├── docs/
│   ├── MANIFESTO-DEV-IA.md
│   ├── MEMORY.md
│   ├── SPRINTS-MVP.md
│   ├── sessoes/
│   │   └── sprints/
│   │       └── sprint-1-seu-app-YYYY-MM-DD.md
│   └── templates/
│       ├── SPRINTS-CHECKLIST-TEMPLATE.md
│       ├── sprint-template.md
│       └── memoria-sessao-sprint-template.md
├── .github/
│   └── prompts/
│       └── plan-setup-governanca.prompt.md
├── apps/
│   ├── app-1/
│   │   ├── SPRINTS-CHECKLIST.md
│   │   └── sprints/
│   │       ├── sprint-1.md
│   │       ├── sprint-2.md
│   │       └── sprint-N.md
│   └── app-2/
│       ├── SPRINTS-CHECKLIST.md
│       └── sprints/
└── README.md
```

## Regra Principal

> **Sprint-Primeiro Obrigatório**
>
> Nenhuma mudança técnica inicia fora de sprint. Toda ação deve estar documentada em `apps/<app>/sprints/sprint-N.md` **antes** da execução técnica.

## Referências

- **INSTALL.md** — Guia passo-a-passo de instalação
- **CHANGELOG.md** — Histórico e atualizações do manifesto
- **FAQ.md** — Dúvidas comuns e troubleshooting
- **LICENSE** — Licença MIT

## Support

Para dúvidas:

1. Leia `FAQ.md` para problemas comuns
2. Consulte `docs/MANIFESTO-DEV-IA.md` para regras
3. Adapte `docs/MEMORY.md` para seu contexto
4. Mantenha `docs/sessoes/sprints/` atualizado por data em cada sessão da sprint
5. Crie issue no repositório com `[question]` no título

## Licença

MIT - Você é livre para usar, copiar e adaptar este template.
