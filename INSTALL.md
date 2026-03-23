# INSTALL.md - Guia de Instalação

Guia passo-a-passo para implementar o template de governança em um novo projeto.

## Pré-requisitos

- Git instalado e configurado
- Editor de markdown (VS Code, Sublime, etc)
- Acesso de escrita ao repositório
- ~30-45 minutos para execução ou 1-2 horas para execução manual

## Passo-a-Passo

### Fase 1: Preparar Estrutura de Pastas

#### 1.1 Criar diretório `docs/`

```bash
cd seu-projeto
mkdir -p docs
mkdir -p docs/sessoes/sprints
mkdir -p .github/prompts
```

#### 1.2 Criar `sprints/` em cada app

Se seu projeto tem múltiplos apps, crie:

```bash
mkdir -p apps/app-1/sprints
mkdir -p apps/app-2/sprints
# ... para cada app
```

#### 1.3 Verificar estrutura

```bash
tree -L 2 -I 'node_modules'
# Ou
find . -type d -name "docs" -o -name ".github" -o -name "sprints"
```

Deve incluir tambem a pasta `docs/sessoes/sprints` para memoria de sessao por sprint.

### Fase 2: Copiar Arquivos Essenciais

#### 2.1 Copiar manifesto

Copie `docs/MANIFESTO-DEV-IA.md` deste template para seu projeto:

```bash
cp governance-manifesto-template/docs/MANIFESTO-DEV-IA.md seu-projeto/docs/
```

**Ou** referencie centralizadamente:

```bash
# Se quer reutilizar um único manifesto em vários projetos
ln -s /caminho/central/MANIFESTO-DEV-IA.md seu-projeto/docs/MANIFESTO-DEV-IA.md
```

#### 2.2 Copiar templates

```bash
cp governance-manifesto-template/docs/MEMORY.md seu-projeto/docs/
cp governance-manifesto-template/docs/SPRINTS-MVP.md seu-projeto/docs/
cp -r governance-manifesto-template/templates seu-projeto/docs/
```

O diretório de templates inclui `memoria-sessao-sprint-template.md` para registro por data de cada sessão da sprint.

#### 2.3 Copiar planos

```bash
cp -r governance-manifesto-template/.github seu-projeto/
```

### Fase 3: Adaptar ao Seu Projeto

#### 3.1 Editar MEMORY.md

```bash
nano seu-projeto/docs/MEMORY.md
```

Preencher:

- `<nome-do-projeto>` com o nome real
- `<atualizacao-mais-recente>` com o estado atual
- `<tech-stack>` com tecnologias utilizadas

Exemplo:

```markdown
- Projeto: Health Platform
- Foco atual: Implementação de governança
- Stack principal: React + TypeScript + Node.js
```

#### 3.2 Editar plan-setup-governanca.prompt.md

```bash
nano seu-projeto/.github/prompts/plan-setup-governanca.prompt.md
```

Substituir placeholders como:

- `<app>` pelos names reais das apps
- `<arquivo-alvo>` pelos arquivos específicos
- Ajustar dependências conforme seu stack

#### 3.3 Criar SPRINTS-CHECKLIST.md por app

Para cada app:

```bash
cp docs/templates/SPRINTS-CHECKLIST-TEMPLATE.md apps/app-1/SPRINTS-CHECKLIST.md
nano apps/app-1/SPRINTS-CHECKLIST.md
```

Editar:

- Adicionar primeira linha com `Sprint 1 | app-1 | planejada | ...`
- Ajustar referências de caminhos (usar `../docs/` para referenciar)

#### 3.4 Criar memoria de sessao inicial da sprint

```bash
mkdir -p docs/sessoes/sprints
cp docs/templates/memoria-sessao-sprint-template.md docs/sessoes/sprints/sprint-1-app-1-YYYY-MM-DD.md
nano docs/sessoes/sprints/sprint-1-app-1-YYYY-MM-DD.md
```

Preencher:

- Data da sessao
- Acao executada
- Arquivos alterados
- Validacao executada
- Commit (quando houver)

### Fase 4: Criar Primeira Sprint

#### 4.1 Copiar template de sprint

```bash
cp docs/templates/sprint-template.md apps/app-1/sprints/sprint-1.md
nano apps/app-1/sprints/sprint-1.md
```

#### 4.2 Preencher snapshot operacional

```markdown
- App/Escopo: app-1
- Status: planejada
- Data de inicio: 2026-03-18
- Data planejada de conclusao: 2026-03-20
- Blocker principal: nenhum
- Proxima acao: preencher objetivo e escopo
```

#### 4.3 Definir objetivo, escopo e checklist

Seguir instruções em `docs/MANIFESTO-DEV-IA.md` para estrutura obrigatória.

#### 4.4 Vincular a memoria de sessao na sprint

No arquivo da sprint (`apps/<app>/sprints/sprint-1.md`), manter referência para a memória de sessão mais recente em `docs/sessoes/sprints/`.

### Fase 5: Commit Inicial de Governança

#### 5.1 Verificar status

```bash
git status
```

Verificar arquivos:

- [ ] `docs/MANIFESTO-DEV-IA.md`
- [ ] `docs/MEMORY.md`
- [ ] `docs/SPRINTS-MVP.md`
- [ ] `docs/templates/*`
- [ ] `docs/sessoes/sprints/sprint-1-app-1-YYYY-MM-DD.md`
- [ ] `.github/prompts/plan-setup-governanca.prompt.md`
- [ ] `apps/*/SPRINTS-CHECKLIST.md`
- [ ] `apps/*/sprints/sprint-1.md`

#### 5.2 Fazer commit

```bash
git add docs/ .github/prompts/ apps/*/SPRINTS-CHECKLIST.md
git commit -m "docs(governança): inicia setup de manifesto"
git push origin main
```

### Fase 6: Validação Final

#### 6.1 Verificar estrutura

```bash
# Validar que todos os arquivos existem
test -f docs/MANIFESTO-DEV-IA.md && echo "✓ Manifesto"
test -f docs/MEMORY.md && echo "✓ Memory"
test -d docs/sessoes/sprints && echo "✓ Memoria de sessao por sprint"
test -d .github/prompts && echo "✓ Prompts"
find apps -name "SPRINTS-CHECKLIST.md" | wc -l
find apps -name "sprint-*.md" | wc -l
```

#### 6.2 Verificar referências

```bash
# Confirmar que MANIFESTO-DEV-IA.md não tem placeholders desnecessários
grep -n "<" docs/MANIFESTO-DEV-IA.md | head -5
```

Deve estar vazio ou apenas com exemplos propositais.

#### 6.3 Verificar links relativos

```bash
# Confirmar que caminhos usam ../ apropriadamente
grep "docs/" apps/*/SPRINTS-CHECKLIST.md | head -3
# Deve mostrar: "../../docs/MANIFESTO-DEV-IA.md" ou similar
```

## Troubleshooting

### Problema: Não consigo editar arquivos

**Solução**: Verificar permissões

```bash
ls -la docs/
# Se não tem permissão de escrita, execute:
chmod 644 docs/*.md
```

### Problema: Git não quer fazer commit

**Solução**: Verificar `.gitignore`

```bash
cat .gitignore | grep -E "docs|\.github"
# Se bloqueia estes diretórios, editar .gitignore ou usar:
git add -f docs/ .github/
```

### Problema: Caminhos relativos não funcionam

**Solução**: Usar caminhos relativos corretos

- De `apps/app-1/SPRINTS-CHECKLIST.md` para `docs/MANIFESTO-DEV-IA.md`: `../../docs/MANIFESTO-DEV-IA.md`
- De `apps/app-1/sprints/sprint-1.md` para `MANIFESTO-DEV-IA.md`: `../../../docs/MANIFESTO-DEV-IA.md`

Verificar com:

```bash
cat apps/app-1/SPRINTS-CHECKLIST.md | grep "\[.*/docs/"
```

## Próximos Passos

Após instalação:

1. **Adaptar MEMORY.md** com estado real das aplicações
2. **Criar primeira sprint detalhada** baseada em prioridades do projeto
3. **Atualizar memória de sessão por data** a cada sessão de execução da sprint
4. **Treinar time** sobre regra sprint-primeiro obrigatório
5. **Ler manifesto completo** em `docs/MANIFESTO-DEV-IA.md`
6. **Consultar FAQ.md** para dúvidas frequentes

## Tempo Estimado

- **Fase 1** (Estrutura): 5 minutos
- **Fase 2** (Copiar): 2 minutos
- **Fase 3** (Adaptar): 10 minutos
- **Fase 4** (Primeira sprint): 10 minutos
- **Fase 5** (Commit): 2 minutos
- **Fase 6** (Validação): 5 minutos

**Total: ~35 minutos**

## Support

Problemas? Consulte:

- [FAQ.md](FAQ.md) - Dúvidas comuns
- [README.md](README.md) - Visão geral
- [docs/MANIFESTO-DEV-IA.md](docs/MANIFESTO-DEV-IA.md) - Regras detalhadas
