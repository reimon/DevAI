# Sprint MVP: Baseline e Descoberta do Projeto

## Snapshot Operacional

- App/Escopo: `<seu-projeto>`
- Status: `planejada`
- Data de inicio: `YYYY-MM-DD`
- Data planejada de conclusao: `YYYY-MM-DD`
- Data real de conclusao: `a preencher`
- Ultima atualizacao: `YYYY-MM-DD`
- Blocker principal: nenhum
- Proxima acao: adaptar este template ao seu contexto

## Objetivo

Esta sprint inicial estabelece o baseline de governança do projeto, criando a estrutura mínima de sprints, memória institucional e planos de execução conforme o manifesto.

Resultado esperado: Projeto estruturado para começar a seguir a governança padrão, com manifesto como fonte de verdade, memoria versionada e primeira sprint concluída.

## Escopo incluido

- [ ] Estrutura de pastas (docs/, .github/prompts/, sprints/)
- [ ] Arquivo MANIFESTO-DEV-IA.md copiado ou referenciado
- [ ] MEMORY.md criado e preenchido com snapshot inicial
- [ ] SPRINTS-CHECKLIST.md por app criado
- [ ] plan-setup-governanca.prompt.md adaptado ao projeto
- [ ] Primeiro commit de governança executado

## Fora do escopo

- Implementação técnica de features ou correções
- Configuração de CI/CD ou pipelines
- Infraestrutura ou provisionamento
- Integrações externas ou APIs

## Entregaveis

- [ ] E1. Diretório `docs/` com MANIFESTO-DEV-IA.md e MEMORY.md
- [ ] E2. Diretório `.github/prompts/` com plan-setup-governanca.prompt.md
- [ ] E3. Arquivo SPRINTS-CHECKLIST.md em cada app
- [ ] E4. Primeiro commit de governança em git

## Checklist de Acoes

### Bloco 1: Estrutura de Pastas

- [ ] 1.1 Criar diretório `docs/` na raiz do projeto
  - Arquivo(s): `docs/`
  - Validacao: `[ -d docs ] && echo "OK"`
  - Evidencia: screenshot ou `ls -la docs/`

- [ ] 1.2 Criar diretório `.github/prompts/`
  - Arquivo(s): `.github/prompts/`
  - Validacao: `[ -d .github/prompts ] && echo "OK"`
  - Evidencia: screenshot ou `ls -la .github/prompts/`

- [ ] 1.3 Criar diretórios `sprints/` em cada app
  - Arquivo(s): `apps/<app>/sprints/`
  - Validacao: `ls -la apps/*/sprints/`
  - Evidencia: listing de diretórios criados

### Bloco 2: Arquivos Canônicos

- [ ] 2.1 Copiar ou referenciar MANIFESTO-DEV-IA.md
  - Arquivo(s): `docs/MANIFESTO-DEV-IA.md`
  - Validacao: `[ -f docs/MANIFESTO-DEV-IA.md ] && echo "OK"`
  - Evidencia: `wc -l docs/MANIFESTO-DEV-IA.md`

- [ ] 2.2 Criar MEMORY.md inicial
  - Arquivo(s): `docs/MEMORY.md`
  - Validacao: `[ -f docs/MEMORY.md ] && echo "OK"`
  - Evidencia: `head -20 docs/MEMORY.md`

- [ ] 2.3 Adaptar plan-setup-governanca.prompt.md
  - Arquivo(s): `.github/prompts/plan-setup-governanca.prompt.md`
  - Validacao: `[ -f .github/prompts/plan-setup-governanca.prompt.md ] && echo "OK"`
  - Evidencia: `wc -l .github/prompts/plan-setup-governanca.prompt.md`

### Bloco 3: Índices de Portfolio

- [ ] 3.1 Criar SPRINTS-CHECKLIST.md para cada app
  - Arquivo(s): `apps/<app>/SPRINTS-CHECKLIST.md`
  - Validacao: `ls apps/*/SPRINTS-CHECKLIST.md`
  - Evidencia: listing dos arquivos criados

## Dependencias Tecnologicas

- Git (para versionamento)
- Editor de markdown (para documentação)
- Acesso ao repositório do projeto
- Nenhuma dependência de biblioteca ou framework

## Notas de Seguranca

Não se aplica.

## Delta desde a ultima atualizacao

`YYYY-MM-DD` - Sprint criada com estrutura inicial e checklist padrão.

## Riscos / Blockers / ETA

- Risco baixo: Esta é uma sprint de estruturação, sem código técnico.
- Dependência: Acesso e permissão de escrita no repositório Git.
- ETA: 30 a 45 minutos para agente IA, 1-2 horas para execução manual.

## Evidencias de Implementacao

- [ ] Diretório `docs/` criado com arquivos
- [ ] Diretório `.github/prompts/` criado com plan
- [ ] SPRINTS-CHECKLIST.md criado em cada app
- [ ] MEMORY.md preenchido com snapshot inicial
- [ ] Git status limpo e pronto para commit

## Commits Executados

- `<hash-curto>` - `docs(governança): inicia setup de manifesto` - estrutura inicial

## Resumo das Atividades

| Acao | O que foi feito                         | Arquivos alterados                                |
| ---- | --------------------------------------- | ------------------------------------------------- |
| 1.1  | Criou diretório docs/                   | `docs/`                                           |
| 1.2  | Criou diretório .github/prompts/        | `.github/prompts/`                                |
| 1.3  | Criou sprints/ em cada app              | `apps/*/sprints/`                                 |
| 2.1  | Copiou MANIFESTO-DEV-IA.md              | `docs/MANIFESTO-DEV-IA.md`                        |
| 2.2  | Criou MEMORY.md                         | `docs/MEMORY.md`                                  |
| 2.3  | Adaptou plan-setup-governanca.prompt.md | `.github/prompts/plan-setup-governanca.prompt.md` |
| 3.1  | Criou SPRINTS-CHECKLIST.md em cada app  | `apps/*/SPRINTS-CHECKLIST.md`                     |

## Pendencias para a Proxima Sprint

- Preencher MEMORY.md com estado real do projeto (apps, services, status)
- Criar primeira sprint detalhada de feature/mudança técnica
- Ajustar caminhos e referências nos templates para contexto específico

## Regras

- Seguir `docs/MANIFESTO-DEV-IA.md` para todas as sprints futuras
