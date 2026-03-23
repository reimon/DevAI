# Manifesto de Gestao de Desenvolvimento para IA

Este manifesto define regras obrigatorias para planejamento, execucao, rastreabilidade e encerramento de mudancas no sistema.

## Objetivos de governanca

- Padronizar a estrutura de todas as sprints.
- Melhorar rastreabilidade tecnica, operacional e historica.
- Reduzir ambiguidade e retrabalho na leitura por humanos e LLMs.
- Melhorar visibilidade, monitoramento e handoff entre sessoes e times.

## Regras obrigatorias

1. Toda mudanca principal deve estar registrada em sprint antes da execucao tecnica.
2. Nenhuma alteracao de sistema inicia fora de sprint.
3. O arquivo detalhado da sprint e a fonte primaria de contexto da mudanca.
4. O arquivo `SPRINTS-CHECKLIST.md` de cada app e um indice resumido e deve espelhar, no minimo, titulo, status e datas principais da sprint.
5. Cada sprint deve informar obrigatoriamente:
   - app ou escopo principal
   - status
   - data de inicio
   - data planejada de conclusao
   - data real de conclusao
   - ultima atualizacao
6. Datas devem usar formato ISO `YYYY-MM-DD`.
7. Status permitidos de sprint:
   - `planejada`
   - `em andamento`
   - `bloqueada`
   - `concluida`
   - `cancelada`
8. Toda sprint deve conter checklist numerado. O formato padrao e `1.1`, `1.2`, `2.1` e assim por diante.
9. Toda acao marcada como concluida deve ter pelo menos uma evidencia minima associada: arquivo alterado, validacao executada, commit, teste, log, screenshot, link de deploy ou artefato equivalente.
10. Se surgir problema, impedimento, mudanca de escopo ou nova necessidade durante a execucao:
    - atualizar a sprint primeiro
    - executar a acao tecnica depois
11. Toda sprint deve manter rastreabilidade de decisoes, validacoes, resultados e pendencias.
12. Toda sprint deve ter uma secao final com resumo das atividades executadas, contendo:
    - acao
    - o que foi feito
    - arquivos alterados
13. Toda sprint deve ter uma secao de commits executados, com lista dos commits feitos durante a execucao.
14. Toda sprint deve ter uma secao clara de evidencias de implementacao.
15. Toda sprint deve registrar pendencias que precisam ser carregadas para a proxima sprint.
16. Toda sprint deve registrar dependencias tecnologicas relevantes.
17. Toda sprint que tocar autenticacao, dados sensiveis, integracoes externas, infraestrutura, permissao ou segredos deve conter notas de seguranca. Se nao se aplicar, preencher `Nao se aplica`.
18. Em infraestrutura, Terraform e a abordagem padrao para provisionamento e ajustes.
19. Toda sprint em andamento deve manter um arquivo de memoria de sessao versionado, vinculado ao arquivo principal da sprint.
20. A memoria de sessao da sprint deve registrar data da sessao e entregas de codigo realizadas.
21. O nome da memoria de sessao deve seguir padrao unico com sprint e data, evitando nomes livres.
22. Cada atualizacao da memoria de sessao deve conter, no minimo: data, acao, arquivos alterados, validacao executada e commit relacionado quando houver.
23. A sprint so pode ser marcada como `concluida` se a memoria de sessao estiver atualizada e referenciada no arquivo da sprint.

## Criterios de transicao de status

- `planejada`: sprint criada, escopo definido, execucao tecnica ainda nao iniciada.
- `em andamento`: execucao tecnica iniciada e ainda sem fechamento total.
- `bloqueada`: execucao interrompida por impedimento tecnico, operacional, dependencia externa ou decisao de negocio.
- `concluida`: entregaveis previstos finalizados, validacoes registradas e pendencias residuais explicitamente movidas para sprint futura.
- `cancelada`: sprint encerrada sem entrega completa, com motivo registrado.

## Processo operacional para mudancas

1. Registrar ou atualizar a sprint.
2. Preencher snapshot operacional, objetivo, escopo, checklist numerado e dependencias antes da mudanca tecnica.
3. Executar a mudanca tecnica.
4. Validar local, testes e CI/CD quando aplicavel.
5. Atualizar checklist, delta, evidencias, commits e resumo das atividades.
6. Atualizar o indice `SPRINTS-CHECKLIST.md` correspondente.
7. Registrar aprendizado relevante em memoria persistente.
8. Atualizar a memoria de sessao da sprint com data e entregas de codigo da sessao.

## Estrutura obrigatoria de cada sprint

Toda sprint deve seguir esta ordem fixa de secoes:

1. Titulo da sprint.
2. Snapshot operacional.
3. Objetivo.
4. Escopo incluido.
5. Fora do escopo.
6. Entregaveis.
7. Checklist de acoes numerado.
8. Dependencias tecnologicas.
9. Notas de seguranca.
10. Delta desde a ultima atualizacao.
11. Riscos, blockers e ETA.
12. Evidencias de implementacao.
13. Commits executados.
14. Resumo das atividades.
15. Pendencias para a proxima sprint.
16. Regras de referencia ao manifesto.

## Regras de preenchimento das secoes

### 1. Snapshot operacional

Deve ficar no topo da sprint e conter, no minimo:

- app ou escopo
- status
- data de inicio
- data planejada de conclusao
- data real de conclusao
- ultima atualizacao
- blocker principal
- proxima acao

Se algum campo ainda nao existir, preencher `a preencher` em vez de omitir.

### 2. Checklist de acoes numerado

- Toda acao deve ser numerada.
- O formato recomendado e:
  - `- [ ] 1.1 Descricao da acao`
  - `- [x] 1.2 Descricao da acao`
- Quando fizer sentido, cada acao pode ter subcampos curtos:
  - `Arquivo(s)`
  - `Validacao`
  - `Dependencia`
  - `Evidencia`

### 3. Resumo das atividades

Ao final da sprint, deve existir um resumo consolidado das atividades executadas.

Formato minimo obrigatorio por item:

- acao
- o que foi feito
- arquivos alterados

Tabela recomendada:

| Acao | O que foi feito | Arquivos alterados |
| ---- | --------------- | ------------------ |
| 1.1  | ...             | ...                |

### 4. Commits executados

Cada sprint deve listar os commits feitos durante a execucao, com:

- hash curto
- mensagem
- finalidade resumida

Formato recomendado:

- `abc1234` - `feat(auth): cria login do paciente` - backend e contexto inicial

### 5. Evidencias de implementacao

Toda sprint deve registrar evidencias claras e verificaveis, por exemplo:

- comando executado e resultado
- teste manual validado
- screenshot
- log relevante
- artefato de CI
- link de deploy ou PR

### 6. Pendencias para a proxima sprint

Deve listar tudo o que falta para fechar o fluxo completo ou o que foi deliberadamente adiado.

Cada pendencia deve informar, quando possivel:

- o item pendente
- motivo
- impacto
- sprint alvo ou proxima acao

### 7. Dependencias tecnologicas

Deve registrar, quando aplicavel:

- bibliotecas e SDKs
- servicos externos
- endpoints ou APIs dependentes
- permissoes necessarias
- versoes ou incompatibilidades conhecidas

### 8. Notas de seguranca

Obrigatorio para qualquer sprint que toque auth, segredos, dados sensiveis, infra, integracoes ou permissoes.

Exemplos do que registrar:

- estrategia de validacao de token
- politica de expiracao
- armazenamento de segredos
- hardening de entrada
- limitacoes de permissao
- itens de seguranca ainda pendentes

## Regras para melhorar governanca, visibilidade e monitoramento

1. Toda sprint deve manter um `blocker principal` e uma `proxima acao` no topo.
2. Toda sprint em andamento ou bloqueada deve atualizar a secao `Delta desde a ultima atualizacao` a cada mudanca relevante.
3. Toda sprint deve ter `Escopo incluido` e `Fora do escopo` para reduzir ambiguidade.
4. Toda sprint deve manter uma lista curta de arquivos impactados dentro do checklist ou no resumo final.
5. Toda sprint deve registrar riscos e ETA quando houver impeditivos ou dependencias externas.
6. A sprint detalhada deve ser suficiente para handoff sem depender de memoria informal.
7. Toda sprint em andamento deve manter referencia para o arquivo de memoria de sessao mais recente.

## Regras para reduzir uso de tokens por LLMs

1. Usar sempre a mesma ordem de secoes em toda sprint.
2. Manter um snapshot operacional curto no topo para leitura rapida.
3. Atualizar a secao `Delta desde a ultima atualizacao` em vez de reescrever a sprint inteira a cada mudanca.
4. Evitar narrativas longas quando uma tabela ou lista curta resolver.
5. Evitar duplicar informacao entre checklist, resumo e evidencias; cada secao deve ter um papel claro.
6. Usar `Escopo incluido` e `Fora do escopo` para reduzir interpretacao ambigua por agentes.
7. Preferir tabelas curtas para commits, resumo das atividades e evidencias.
8. Quando uma sprint ainda estiver apenas planejada, registrar o minimo necessario para execucao e expandir detalhes conforme a implementacao avanca.

## Governanca do MEMORY.md (complemento da memoria interna do agente)

### Importancia e papel no desenvolvimento

- `docs/MEMORY.md` e a memoria institucional versionada do repositorio.
- Deve complementar a memoria interna do agente e a memoria persistente externa, nunca substituir sprint detalhada.
- Ajuda a reduzir retrabalho, acelerar retomada de contexto e manter consistencia entre sessoes.

### Local de armazenamento

- Local oficial: `docs/MEMORY.md`.
- Nao criar multiplas versoes de memoria fora de `docs/`.
- Toda referencia legada ao arquivo de memoria da raiz deve ser migrada para `docs/MEMORY.md`.

### Diretrizes de construcao e padronizacao

1. Estrutura minima obrigatoria:

- snapshot rapido
- estado atual por dominio
- pendencias ativas
- regras operacionais estaveis
- comandos essenciais
- historico recente

2. Conteudo deve ser curto, verificavel e orientado a decisao.
3. Evitar duplicacao do conteudo detalhado de sprint; referenciar `sprint-N.md` quando necessario.
4. Nao registrar segredos, credenciais ou dados sensiveis.
5. Atualizar o MEMORY em marcos relevantes (fim de sprint, mudanca de baseline, decisao estrutural).

### Quando o agente deve ler o MEMORY (agilidade e economia de contexto)

1. Ler sob demanda, nao em toda tarefa.
2. Ler quando houver retomada de contexto entre sessoes/sprints ou handoff entre agentes/pessoas.
3. Ler quando a tarefa envolver multiplos arquivos, mudanca arquitetural ou decisao operacional sensivel.
4. Ler quando o usuario pedir consolidacao de status, plano amplo ou auditoria.
5. Nao ler para tarefas pequenas e isoladas sem dependencia historica.
6. Ordem recomendada:

- primeiro `Snapshot rapido` e `Pendencias ativas`
- depois secoes especificas conforme a necessidade
- evitar releitura completa no mesmo turno sem alteracao do arquivo

## Memoria de sessao por sprint (registro operacional do agente)

### Objetivo

- Complementar o arquivo da sprint com um log curto e verificavel da execucao por sessao.
- Facilitar retomada de contexto entre sessoes do Copilot sem reconstituir historico manualmente.

### Local de armazenamento

- Pasta padrao: `docs/sessoes/sprints/`.
- Cada sprint deve ter arquivos de sessao separados por data.

### Padrao de nome

- Formato: `sprint-<numero>-<escopo-curto>-YYYY-MM-DD.md`.
- Exemplo: `sprint-26-patient-auth-2026-03-18.md`.

### Campos obrigatorios

- Sprint
- App ou escopo
- Data da sessao
- Arquivo da sprint relacionado
- Status da sprint na data
- Entregas de codigo da sessao
- Validacoes executadas
- Commits relacionados
- Pendencias para a proxima sessao

### Regras de preenchimento

- Registrar somente data, sem horario.
- Manter conteudo objetivo e orientado a evidencia.
- Registrar apenas o delta da sessao, sem duplicar toda a sprint.
- Nunca registrar segredos, credenciais ou dados sensiveis.

### Regra de fechamento

- Antes de marcar a sprint como `concluida`, confirmar que existe memoria de sessao atualizada e referenciada no arquivo da sprint.

## Governanca de sprints

- Cada sprint deve ter seu proprio arquivo: `sprints/sprint-<numero>.md` dentro do app correspondente.
- Exemplo: `apps/admin-expo/sprints/sprint-11.md`, `apps/patient-expo/sprints/sprint-8.md`.
- O arquivo `SPRINTS-CHECKLIST.md` em cada app e apenas um indice de portfolio; nao contem o contexto completo da sprint.
- Novas sprints devem ser criadas como arquivos separados antes da execucao tecnica.
- Sprints antigas podem ser migradas gradualmente para o novo formato quando houver necessidade operacional.

## Template oficial de sprint

Copiar e preencher o modelo abaixo para toda nova sprint.

```markdown
# Sprint N: Titulo da Sprint

## Snapshot Operacional

- App/Escopo: a preencher
- Status: planejada
- Data de inicio: YYYY-MM-DD
- Data planejada de conclusao: YYYY-MM-DD
- Data real de conclusao: a preencher
- Ultima atualizacao: YYYY-MM-DD
- Blocker principal: nenhum
- Proxima acao: a preencher

## Objetivo

Descrever em 1 ou 2 paragrafos o resultado esperado da sprint.

## Escopo incluido

- Item 1
- Item 2

## Fora do escopo

- Item 1
- Item 2

## Entregaveis

- [ ] E1. Entregavel principal
- [ ] E2. Entregavel principal

## Checklist de Acoes

### Bloco 1: Tema

- [ ] 1.1 Acao detalhada
  - Arquivo(s): `path/to/file.ts`
  - Validacao: `npm run check`
  - Evidencia: a preencher

- [ ] 1.2 Acao detalhada
  - Arquivo(s): `path/to/file.ts`
  - Dependencia: a preencher
  - Evidencia: a preencher

### Bloco 2: Tema

- [ ] 2.1 Acao detalhada
  - Arquivo(s): `path/to/file.ts`
  - Validacao: teste manual
  - Evidencia: a preencher

## Dependencias Tecnologicas

- Biblioteca/SDK: nome e versao
- Servico externo: nome
- Permissoes: a preencher
- Incompatibilidades conhecidas: nenhuma

## Notas de Seguranca

- Item 1
- Item 2
- Se nao se aplicar, escrever `Nao se aplica`.

## Delta desde a ultima atualizacao

- YYYY-MM-DD: resumo curto do que mudou desde a ultima revisao.

## Riscos / Blockers / ETA

- Risco ou blocker atual
- Impacto
- ETA ou proxima revisao

## Evidencias de Implementacao

- `npm run check` executado com sucesso
- Teste manual validado
- Screenshot/log/link de PR/deploy

## Commits Executados

- `abc1234` - `mensagem do commit` - finalidade resumida
- `def5678` - `mensagem do commit` - finalidade resumida

## Resumo das Atividades

| Acao | O que foi feito     | Arquivos alterados       |
| ---- | ------------------- | ------------------------ |
| 1.1  | Descrever resultado | `path/a.ts`, `path/b.ts` |
| 1.2  | Descrever resultado | `path/c.ts`              |

## Pendencias para a Proxima Sprint

- Pendencia 1 - motivo - proxima acao
- Pendencia 2 - motivo - sprint alvo

## Memoria de Sessao da Sprint

- Arquivo: `docs/sessoes/sprints/sprint-N-escopo-YYYY-MM-DD.md`
- Data da sessao: YYYY-MM-DD
- Ultima atualizacao: YYYY-MM-DD
- Status da memoria de sessao: atualizado | pendente

## Regras

- Seguir `docs/MANIFESTO-DEV-IA.md`.
```

## Guia rapido de preenchimento

- O que e obrigatorio: snapshot operacional, objetivo, checklist numerado, dependencias tecnologicas, notas de seguranca, evidencias, commits, resumo das atividades e pendencias.
- O que pode ser curto: escopo, delta, riscos e notas, desde que continuem claros.
- O que nunca deve ser omitido em sprint concluida: data real de conclusao, evidencias, commits executados e resumo das atividades.
- O que nunca deve ficar ambiguo: status, blocker principal, proxima acao e o que ficou pendente.

## Escopo de aplicacao

- `docs/SPRINTS-MVP.md`
- `apps/admin-expo/SPRINTS-CHECKLIST.md` (indice)
- `apps/admin-expo/sprints/sprint-N.md` (arquivos individuais de sprint)
- `apps/patient-expo/SPRINTS-CHECKLIST.md` (indice)
- `apps/patient-expo/sprints/sprint-N.md` (arquivos individuais de sprint)
- `docs/MEMORY.md` (arquivo canonico)
- `.github/prompts/` (planos de execucao e onboarding do agente)

## Planos de execucao do agente (.github/prompts/)

### O que sao e por que sao fundamentais

Os arquivos `.github/prompts/*.prompt.md` sao roteiros estruturados que o agente de IA usa como instrucao pre-definida para executar iniciativas completas de governanca e desenvolvimento.

Sem eles, o manifesto define **o que deve ser feito**, mas o agente nao sabe **como comecar**, em qual ordem executar as fases, quais arquivos tocar e quais criterios validar ao final. O arquivo de plano e o elo operacional entre as regras do manifesto e a execucao real pelo agente.

Em resumo:

- O manifesto define as regras.
- O `docs/MEMORY.md` guarda o estado do projeto.
- O `.github/prompts/*.prompt.md` instrui o agente a executar as regras sobre o estado real.

### Quando criar um arquivo de plano

- Ao iniciar uma nova iniciativa de governanca, migracao, padronizacao ou onboarding.
- Quando uma tarefa tem mais de 3 fases dependentes entre si.
- Quando o agente precisa de contexto pre-existente antes de agir (arquivos-alvo, decisoes ja tomadas, escopo excluido).
- Quando a iniciativa deve ser repetivel ou reutilizavel em outros projetos.

### Onde salvar

- Local padrao: `.github/prompts/<nome-descritivo>.prompt.md`.
- Nomear com prefixo descritivo do objetivo: `plan-`, `onboarding-`, `migracao-`, `setup-`.
- Cada iniciativa tem seu proprio arquivo; nao misturar planos distintos.

### Estrutura obrigatoria do arquivo de plano

Todo arquivo de plano deve conter as seguintes secoes, nesta ordem:

1. **Titulo e descricao resumida** — objetivo da iniciativa em 1 a 2 linhas.
2. **Status** — `EM ANDAMENTO` ou `CONCLUIDO`, com data de ultima atualizacao.
3. **Fases** — lista numerada de passos com dependencias explicitas (`_depends on N_`, `_blocks N_`).
4. **Arquivos de referencia** — tabela com caminho e papel de cada arquivo envolvido.
5. **Verificacao** — criterios que o agente deve checar ao final para confirmar execucao correta.
6. **Decisoes consolidadas** — contexto de escopo e decisoes ja tomadas para evitar retrabalho.

### Regras de manutencao

- Marcar fases concluidas com `[x]` ao final de cada execucao; nunca deletar fases antigas.
- Atualizar `Status` e data sempre que o plano for reutilizado ou retomado.
- Nao usar caminhos absolutos de maquina local; usar caminhos relativos ao repositorio.
- Quando a iniciativa estiver concluida, manter o arquivo como registro historico e referencia para novos projetos.

### Template de exemplo (adaptavel a qualquer projeto)

Copiar o modelo abaixo para criar um novo plano de execucao:

```markdown
## Plan: <Titulo da Iniciativa>

> **Status: EM ANDAMENTO** — <descricao resumida do objetivo>
> Ultima atualizacao: YYYY-MM-DD

<Descricao em 1 a 3 linhas do que esta iniciativa resolve e por que e necessaria.>

---

## Fases

1. [ ] Fase 1 — <nome>: <descricao da acao e arquivo alvo>. _blocks steps 2-N_
2. [ ] Fase 2 — <nome>: <descricao>. _depends on 1_
3. [ ] Fase 3 — <nome>: <descricao>. _depends on 1-2_
4. [ ] Fase 4 — Validacao final: revisar resultados, confirmar criterios e registrar pendencias. _depends on 1-3_

---

## Arquivos de referencia

| Arquivo                     | Papel                                |
| --------------------------- | ------------------------------------ |
| `docs/MANIFESTO-DEV-IA.md`  | Fonte de verdade de governanca       |
| `docs/MEMORY.md`            | Memoria institucional do projeto     |
| `<caminho/arquivo-alvo.md>` | <papel no contexto desta iniciativa> |

---

## Verificacao

1. Confirmar que <criterio 1 verificavel>.
2. Confirmar que <criterio 2 verificavel>.
3. Confirmar que `docs/MEMORY.md` foi atualizado com as decisoes desta iniciativa.
4. Confirmar que nenhuma referencia legada permanece nos arquivos editados.

---

## Decisoes consolidadas

- Escopo confirmado: <o que esta incluido>.
- Excluido desta iniciativa: <o que nao deve ser tocado>.
- Caminho canonico do manifesto: `docs/MANIFESTO-DEV-IA.md`.
- <Decisao adicional relevante para o projeto>.
```

### Prompt de ativacao para adaptar ao seu projeto

Ao copiar o template acima para um novo projeto, usar o seguinte prompt para que o agente adapte o plano ao contexto real antes de executar:

```
Leia o arquivo `.github/prompts/<nome-do-plano>.prompt.md` e adapte-o ao projeto atual:

1. Substitua todos os campos de exemplo (<...>) pelos valores reais do projeto.
2. Leia `docs/MANIFESTO-DEV-IA.md` para entender as regras de governança vigentes.
3. Leia `docs/MEMORY.md` para entender o estado atual do projeto.
4. Ajuste os caminhos de arquivos para refletir a estrutura real do repositório.
5. Identifique quais fases já foram executadas e marque-as como [x].
6. Confirme o escopo e as decisões consolidadas com base no que já existe no projeto.
7. Ao finalizar a adaptação, apresente um resumo das fases pendentes antes de iniciar a execução.
```

## Plan: Setup Inicial de Governanca

> **Status: TEMPLATE** — Passo a passo para implementar o manifesto em um novo projeto
> Ultima atualizacao: 2026-03-18

Este plano descreve como inicializar governanca de desenvolvimento IA em um novo projeto, criando a estrutura minima necessaria para seguir as regras do manifesto.

---

## Fases

1. [ ] **Fase 1 — Criar estrutura de pastas**: Criar diretórios `docs/`, `docs/sessoes/sprints/`, `.github/prompts/`, e `sprints/` dentro de cada app. _blocks steps 2-7_

2. [ ] **Fase 2 — Criar arquivo MANIFESTO-DEV-IA.md**: Copiar o manifesto canonico para `docs/MANIFESTO-DEV-IA.md` no novo projeto ou referenciar o manifesto compartilhado. _depends on 1_

3. [ ] **Fase 3 — Criar arquivo MEMORY.md**: Criar `docs/MEMORY.md` com estrutura minima (snapshot, estado, pendencias, regras, comandos). _depends on 1_

4. [ ] **Fase 4 — Criar SPRINTS-CHECKLIST.md por app**: Criar `apps/<app>/SPRINTS-CHECKLIST.md` como indice inicial de portfolio de sprints. _depends on 1_

5. [ ] **Fase 5 — Criar primeiro arquivo plan-setup-governanca.prompt.md**: Criar `.github/prompts/plan-setup-governanca.prompt.md` com este plano adaptado ao projeto real. _depends on 2-4_

6. [ ] **Fase 6 — Criar primeira sprint de baseline**: Criar `docs/SPRINTS-MVP.md` ou `apps/<app>/sprints/sprint-1.md` registrando o estado inicial do projeto. _depends on 3_

7. [ ] **Fase 7 — Criar memoria de sessao inicial da sprint**: Criar arquivo em `docs/sessoes/sprints/` usando padrão por sprint e data. _depends on 6_

8. [ ] **Fase 8 — Commit inicial de governanca**: Executar `git add` em todos os arquivos criados e fazer commit com prefixo `docs(governança):`. _depends on 5-7_

9. [ ] **Fase 9 — Validacao final**: Confirmar que todas as secoes obrigatorias foram preenchidas, que nenhuma referencia legada permanece, e que o projeto esta pronto para sprints futuras. _depends on 1-8_

---

## Arquivos de referencia

| Arquivo                                           | Papel                                         |
| ------------------------------------------------- | --------------------------------------------- |
| `docs/MANIFESTO-DEV-IA.md`                        | Fonte de verdade de governanca para o projeto |
| `docs/MEMORY.md`                                  | Memoria institucional inicial                 |
| `docs/sessoes/sprints/`                           | Memoria de sessao por sprint e por data       |
| `docs/SPRINTS-MVP.md` ou `SPRINTS-MVP.md`         | Sprint inicial de baseline e descoberta       |
| `apps/<app>/SPRINTS-CHECKLIST.md`                 | Indice de portfolio de sprints por aplicacao  |
| `.github/prompts/plan-setup-governanca.prompt.md` | Este plano adaptado para reutilizacao         |
| `apps/<app>/sprints/sprint-1.md`                  | Primeira sprint detalhada (se aplicavel)      |

---

## Verificacao

1. Confirmar que `docs/` existe e contem `MANIFESTO-DEV-IA.md` e `MEMORY.md`.
2. Confirmar que `.github/prompts/` existe e contem `plan-setup-governanca.prompt.md`.
3. Confirmar que cada app possui `SPRINTS-CHECKLIST.md` na raiz.
4. Confirmar que `docs/SPRINTS-MVP.md` ou equivalente esta preenchido com estado inicial do projeto.
5. Confirmar que `docs/sessoes/sprints/` existe e contem memoria de sessao inicial por sprint e data.
6. Confirmar que nenhuma referencia legada ou placeholder vazio permanece nos arquivos criados.
7. Confirmar que `docs/MEMORY.md` ja contem snapshot rapido, estado por dominio, e pendencias iniciais.
8. Confirmar que o primeiro commit foi executado com mensagem padrao: `docs(governança): inicia setup de manifesto`.

---

## Decisoes consolidadas

- **Escopo confirmado**: Criar estrutura minima de governanca conforme regras obrigatorias do manifesto.
- **Excluido desta iniciativa**: Configuracao de CI/CD, scripts de automacao, ou integracao com ferramentas externas; apenas estrutura de arquivos e conteudo inicial.
- **Caminho canonico do manifesto**: `docs/MANIFESTO-DEV-IA.md` ou referencia remota ao repositorio central.
- **Frequencia de atualizacao**: Este plano pode ser reutilizado para cada novo projeto ou branch importante.
- **Dependencias**: Git, editor de markdown, acesso ao repositorio do projeto.
- **Tempo estimado**: 30 a 45 minutos para um agente IA ou 1 a 2 horas para execucao manual.

---

## Regra de conflito

Se houver conflito entre velocidade e processo, prevalece o processo definido neste manifesto.
