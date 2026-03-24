# FAQ.md - Perguntas Frequentes

Dúvidas comuns sobre uso e implementação do template de governança.

## Geral

### P: O que é sprint-primeiro obrigatório?

**R**: Significa que toda mudança técnica **deve estar documentada em arquivo de sprint** antes de ser executada. Nenhuma linha de código é escrita fora de sprint. Benefícios:

- Rastreabilidade total
- Menos retrabalho
- Melhor handoff entre agentes
- Documentação automática

### P: Preciso usar EXATAMENTE este manifesto?

**R**: O manifesto é rígido no que é **obrigatório** (sprint-primeiro, datas, checklist, evidências), mas flexível no que é **adaptável** (número de apps, tecnologias, nomes de templates).

Você pode:

- ✅ Adaptar caminhos de arquivos
- ✅ Adicionar seções extras após as 16 obrigatórias
- ✅ Usar outros formatos (JSON, Yaml) para dados estruturados
- ❌ Remover seções obrigatórias
- ❌ Mudar ordem das 16 seções
- ❌ Executar ações fora de sprint

### P: Posso usar um único manifesto para múltiplos projetos?

**R**: Sim! Recomendado mesmo. Use symlink:

```bash
ln -s /caminho/central/MANIFESTO-DEV-IA.md seu-projeto-1/docs/
ln -s /caminho/central/MANIFESTO-DEV-IA.md seu-projeto-2/docs/
```

Cada projeto pode ter seu próprio `MEMORY.md` e sprints, mas compartilham as **mesmas regras**.

---

## Instalação e Setup

### P: Quanto tempo leva para fazer setup?

**R**: ~35 minutos com passo-a-passo:

- 5 min: Criar estrutura de pastas
- 2 min: Copiar arquivos
- 10 min: Adaptar ao projeto
- 10 min: Criar primeira sprint
- 5 min: Commit e validação
- 3 min: Troubleshooting

### P: Tenho um projeto existente. Posso adicionar isto retroativamente?

**R**: Sim! Você pode:

1. Copiar estrutura sem remover nada existente
2. Migrar sprints passadas para o formato (opcional, funciona incrementalmente)
3. Começar a usar o formato em novas sprints imediatamente
4. Não é necessário refazer tudo de uma vez

### P: Dá erro ao fazer git add. O que faço?

**R**: Possíveis causas:

```bash
# Causa 1: .gitignore está bloqueando
cat .gitignore | grep -E "docs|\.github"

# Solução: Remover a linha ou usar -f
git add -f docs/ .github/

# Causa 2: Permissões de arquivo
ls -la docs/
chmod 644 docs/*.*
git add docs/

# Causa 3: Arquivos muito grandes
du -sh docs/*
# Se maior que 100MB, considere usar Git LFS
```

### P: Como atualizo os templates depois de instalar?

**R**: Você tem controle total. Se quiser sincronizar com versão central:

```bash
# Opção 1: Copiar manualmente (recomendado)
cp governance-template/docs/MANIFESTO-DEV-IA.md seu-projeto/docs/

# Opção 2: Usar git subtree
git subtree pull --prefix=neural-flow-framework governance-template main

# Opção 3: Usar symlink (para arquivo único)
ln -s /central/MANIFESTO-DEV-IA.md seu-projeto/docs/
```

---

## Sprints

### P: Como começo minha primeira sprint?

**R**: Passo-a-passo rápido:

```bash
# 1. Copiar template
cp docs/templates/sprint-template.md apps/seu-app/sprints/sprint-1.md

# 2. Editar
nano apps/seu-app/sprints/sprint-1.md

# 3. Preencher (mínimo):
# - Snapshot operacional (app, status, datas, blocker, próxima ação)
# - Objetivo (2 parágrafos)
# - Checklist (pelo menos 3 ações)

# 4. Executar ações DEPOIS

# 5. Registrar evidências

# 6. Commit
git add apps/seu-app/sprints/sprint-1.md
git commit -m "docs(sprint): sprint-1 baseline do seu-app"
```

### P: Posso usar sprints com menos ações?

**R**: Sim. A estrutura é flexível em quantidade, mas não em qualidade:

- ✅ Sprint com 1 ação grande é válida
- ✅ Sprint com 20 ações é válida
- ✅ Sprint com duração de 1 dia é válida
- ❌ Sprint sem checklist é inválida
- ❌ Sprint sem snapshot operacional é inválida
- ❌ Ações sem evidência não contam como concluídas

### P: O que fazer se precisar mudar escopo no meio da sprint?

**R**: Primeiro, **atualizar a sprint**:

```markdown
## Delta desde a ultima atualizacao

2026-03-18 10:00 - Escopo expandido: adicionadas 2 ações de validação por mudança de requisito. Sprint agora tem 8 ações em vez de 6.
```

Depois, executar as ações técnicas. Isso deixa tudo rastreável.

### P: Quantas sprints deveriam estar em andamento?

**R**: Recomendação por tamanho de time:

- **1-2 pessoas**: 1 sprint simultânea (foco)
- **3-5 pessoas**: 2-3 sprints (por app ou tema)
- **6+ pessoas**: 3-5 sprints (paralelo, mas coordenado)

Cada sprint mapeia a **comunicação real** do time.

---

## MEMORY.md

### P: Com qual frequência devo atualizar MEMORY.md?

**R**: Atualize em:

- ✅ Fim de cada sprint concluída
- ✅ Mudança de ambiente ou infraestrutura
- ✅ Decisão arquitetural importante
- ✅ Nova dependência crítica
- ❌ **Não** a cada commit (economia de contexto)
- ❌ **Não** para microajustes sem impacto

### P: Quanto deve ter MEMORY.md?

**R**: Máximo 200-300 linhas:

- 5-15 linhas: Snapshot rápido
- 30-50 linhas: Estado por domínio
- 10-20 linhas: Pendências ativas
- Resto: Regras, comandos, histórico

Se exceder 300 linhas, considere que precisa ser dividido em múltiplos arquivos ou que há excesso de detalhamento.

### P: Posso registrar segredos em MEMORY.md?

**R**: **NÃO**. Nunca registre:

- ❌ Senhas, tokens, ou chaves
- ❌ IPs privados ou URLs internas
- ❌ Dados pessoais ou sensíveis
- ❌ Credenciais de acesso

Referencie onde estão guardados (ex: "credenciais em .env.local" ou "secret do GitHub Actions").

### P: Como estruturo estado por domínio?

**R**: Exemplo para projeto multi-app:

```markdown
## Estado atual por dominio

### Admin App

- Status: em andamento
- Última mudança: Sprint 10, 2026-03-15
- Stack: React + TypeScript
- Endpoints críticos: POST /admin/users, GET /admin/reports

### Patient App

- Status: planejada
- Última mudança: n/a
- Stack: React Native + Expo
- Arquivos principais: src/Patient.tsx, src/hooks/useAuth.ts
```

---

## Planos de Execução

### P: Para que servem os planos em .github/prompts/?

**R**: São **instruções estruturadas para agentes IA** executarem iniciativas complexas. Contêm:

- Objetivo e status
- Fases com dependências
- Arquivos envolvicos
- Critérios de verificação
- Decisões já tomadas

Reutilizáveis em múltiplos projetos.

### P: Preciso criar um novo plano?

**R**: Crie um novo plano quando:

- ✅ Iniciativa tem 3+ fases dependentes
- ✅ Agent precisa de contexto pré-existente
- ✅ Tarefa é repetível em múltiplos projetos
- ❌ **Não** para tarefas simples de 1-2 ações

Exemplo de quando criar:

- Migração de framework
- Setup inicial de governança
- Refatoração arquitetural
- Integração com novo serviço externo

---

## Troubleshooting

### P: Git me pede rebase porque manifesto mudou

**R**: Se outro projeto atualizou manifesto central:

```bash
# Opção 1: Fazer rebase (se usar symlink)
git rebase origin/main

# Opção 2: Manter versão local
git merge origin/main
# (Resolve conflito mantendo sua versão)

# Opção 3: Sincronizar manualmente
cp central/MANIFESTO-DEV-IA.md seu-projeto/docs/
git add docs/MANIFESTO-DEV-IA.md
git commit -m "docs: sincroniza manifesto com versão central"
```

### P: Performance: Dá lento ler sprints antigas

**R**: Sprints são arquivos markdown, logo rápidos. Se lentidão:

```bash
# Medir tamanho
find . -name "sprint-*.md" | xargs wc -l | sort -n | tail -10

# Arquivar sprints vencidas (opcional)
mkdir -p archive/2026-Q1
mv apps/*/sprints/sprint-{1..10}.md archive/2026-Q1/

# Atualizar SPRINTS-CHECKLIST.md com referência ao arquivo
```

### P: Tenho 100+ sprints. Como organizo?

**R**: Estratégia de organização:

```
apps/seu-app/
├── sprints/
│   ├── 2025/
│   │   ├── sprint-1.md ... sprint-13.md    (Q1, trimestre 1)
│   ├── 2026/
│   │   ├── Q1/
│   │   │   ├── sprint-1.md ... sprint-13.md
│   │   ├── Q2/
│   │   │   └── sprint-14.md ...
│   └── SPRINTS-CHECKLIST.md (índice master)
```

Atualizar `SPRINTS-CHECKLIST.md` com caminhos relativos:

```markdown
| ... | 2026-Q1 | ... | `2026/Q1/sprint-1.md` |
```

---

## Boas Práticas

### P: Qual é o checklist ideal?

**R**: Equilíbrio:

- **Muito pequeno** (1-2 ações): Não captura complexidade
- **Ideal** (3-8 ações): Detalhe suficiente, ainda rastreável
- **Muito grande** (20+ ações): Difícil de ler, melhor dividir em 2 sprints

### P: Como evidencio commit ou teste?

**R**: Exemplos válidos de evidência:

```markdown
## Evidencias de Implementacao

- Commit 3a7f921: `feat(auth): login paciente`
- Test rodado: `npm run test -- src/hooks/useAuth.test.ts` ✓
- Build rodado: `npm run build` (sucesso)
- Deploy: Pushed para origin/main (2 commits, 0 conflicts)
- Screenshot: Login form funcional em mobile
```

### P: Quando marcar sprint como concluída?

**R**: Quando:

- ✅ Todas ações marcadas `[x]`
- ✅ Todas têm evidência registrada
- ✅ Data real de conclusão preenchida
- ✅ Resumo das atividades completoizado
- ✅ Pendências movidas para sprint seguinte

---

## Contato e Feedback

Dúvida não respondida aqui?

1. Consulte `README.md` para visão geral
2. Consulte `docs/MANIFESTO-DEV-IA.md` para regras detalhadas
3. Consulte `INSTALL.md` para troubleshooting de setup
4. Abra issue no repositório: `[question]` no título
5. Contribua com PR para melhorar FAQ

---

**Última atualização**: 2026-03-18
