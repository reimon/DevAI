# Framework Agora: Desenvolvimento em Parceria com AI

## 1) Proposito

Este framework foi criado para equipes de engenharia que desenvolvem com AI no centro do processo, com foco em cinco pilares:

- Velocidade de entrega com qualidade.
- Uso consciente de tokens com disciplina de FinOps.
- Seguranca de dados, codigo e operacao.
- Governanca clara para reduzir risco e retrabalho.
- Visibilidade e monitoramento de ponta a ponta.

Mensagem central:

Hoje, o desenvolvimento de software e feito em parceria com AI. Nao e opcional. O diferencial competitivo esta em operar essa parceria com metodo.

## 2) Para quem este framework serve

- Liderancas de produto, engenharia e plataforma.
- Tech leads e squads de desenvolvimento.
- Times de seguranca e compliance.
- Times de FinOps e operacao cloud.
- Comunidades e eventos tecnicos focados em AI aplicada.

## 3) Principios base

1. AI acelera, mas nao substitui responsabilidade tecnica.
2. Toda automacao sem observabilidade vira risco oculto.
3. Velocidade sem governanca gera retrabalho caro.
4. Token e custo variavel de engenharia: precisa de meta, dono e controle.
5. Seguranca e requisito de arquitetura, nao etapa final.
6. Melhorar continuamente vale mais que buscar perfeicao inicial.

## 4) Pilares do framework

## Pilar A: Velocidade de Desenvolvimento

### Objetivo

Aumentar throughput de entrega sem degradar qualidade, previsibilidade e manutencao.

### Praticas obrigatorias

- Planejar entregas curtas com escopo claro e fora de escopo explicito.
- Definir criterio de pronto para codigo, teste, seguranca e documentacao.
- Trabalhar com ciclos pequenos de implementacao e validacao.
- Padronizar templates de sprint, PR e mudanca arquitetural.
- Registrar decisoes tecnicas relevantes no momento da mudanca.

### Antipadroes

- Prompt grande sem objetivo claro.
- Reescrever inteiro quando bastava alterar delta.
- Pulso de entrega grande sem checkpoints intermediarios.
- Codegen sem estrategia de teste e rollback.

### Metricas recomendadas

- Lead time por tipo de demanda.
- Tempo de ciclo por PR.
- Taxa de retrabalho por sprint.
- Taxa de regressao pos-release.
- Tempo medio de restauracao em falha.

## Pilar B: FinOps de Tokens

### Objetivo

Tratar token como recurso financeiro e operacional, com previsibilidade de custo e ganho de produtividade mensuravel.

### Modelo de controle

- Orcamento mensal por produto e por time.
- Cota semanal por iniciativa critica.
- Guardrails por contexto (entrada/saida maxima por operacao).
- Estrategia de tiers de modelo:
  - Modelo leve para classificacao, normalizacao, rotinas repetitivas.
  - Modelo medio para code assist e documentacao tecnica.
  - Modelo avancado apenas para tarefas de alta complexidade.

### Politicas praticas de reducao de custo

- Contexto minimo necessario por tarefa.
- Reuso de contexto estruturado (delta em vez de historico completo).
- Cache de respostas e de artefatos intermediarios.
- RAG com recuperacao objetiva para evitar prompt inflado.
- Evitar repeticao de arquivos inteiros sem necessidade.
- Definir limite de tentativas por tarefa antes de escalar para humano.

### KPIs de FinOps AI

- Custo por funcionalidade entregue.
- Tokens por historia concluida.
- Percentual de tarefas resolvidas no primeiro ciclo.
- Custo de retrabalho por erro de geracao.
- Economia estimada por automacao efetiva.

### Formulas de referencia

- Custo total de AI = custo de tokens de entrada + custo de tokens de saida + custo de ferramentas + custo de observabilidade.
- Custo por entrega = custo total de AI no periodo / quantidade de entregas concluidas.
- Produtividade liquida = horas economizadas - horas de retrabalho induzido.

## Pilar C: Seguranca

### Objetivo

Garantir que a parceria com AI nao exponha dados sensiveis, segredos, identidade ou superficie de ataque.

### Controles minimos

- Classificacao de dados antes de enviar contexto para modelo.
- Proibicao explicita de envio de segredo, token, senha ou chave privada.
- Sanitizacao e mascaramento de dados em logs e prompts.
- Validacao de saida gerada antes de executar em producao.
- Escaneamento de dependencia e analise estatica no pipeline.
- Regras de permissao minima para ferramentas e automacoes.

### Riscos especificos em AI

- Prompt injection em contexto externo.
- Exfiltracao de dados por saida de modelo.
- Hallucination com aparencia de certeza.
- Geracao de codigo inseguro por padrao fraco.
- Dependencia excessiva de output sem revisao humana.

### Contramedidas recomendadas

- Lista de bloqueio de termos e padroes sensiveis.
- Validador de output para comandos destrutivos.
- Passagem obrigatoria por revisao humana em mudancas criticas.
- Testes de seguranca para fluxos gerados por AI.
- Trilhas de auditoria para prompts, contexto e decisoes finais.

## Pilar D: Governanca

### Objetivo

Padronizar como decisoes, mudancas e evidencias sao registradas, aprovadas e auditadas.

### Mecanismos chave

- Estrutura unica de sprint para todo o ecossistema.
- Status padronizado e criterios claros de transicao.
- Checklists numerados com evidencia por acao concluida.
- Registro de commits e pendencias para proxima sprint.
- Claridade de dono por acao, risco e decisao.

### Artefatos obrigatorios

- Documento de sprint atualizado.
- Indice de sprint sincronizado.
- Evidencias de validacao (teste, comando, log, PR).
- Registro de risco e plano de mitigacao.

### Integracao com este repositorio

- Diretrizes operacionais de sprint: [../docs/MANIFESTO-DEV-IA.md](../docs/MANIFESTO-DEV-IA.md)
- Memoria institucional da operacao: [../docs/MEMORY.md](../docs/MEMORY.md)

## Pilar E: Visibilidade e Monitoramento

### Objetivo

Tornar a operacao AI observavel, previsivel e auditavel em tempo quase real.

### O que monitorar

- Volume de uso por modelo, time e fluxo.
- Custo por dia, semana, sprint e release.
- Latencia media por tipo de tarefa.
- Taxa de falha por etapa do pipeline.
- Taxa de rollback relacionada a mudanca assistida por AI.
- Qualidade percebida do output (aceite, ajuste, descarte).

### Painel minimo executivo

- Custo acumulado de tokens no mes.
- Orcamento restante e risco de estouro.
- Top 10 fluxos com maior consumo.
- Entregas concluidas por unidade de custo.
- Incidentes de seguranca e conformidade.
- Tendencia de produtividade liquida.

### Alertas recomendados

- Consumo diario acima do limite esperado.
- Aumento abrupto de tokens por tarefa.
- Queda de taxa de aceite de output.
- Regressao de qualidade em release assistido por AI.

## 5) Modelo operacional ponta a ponta

## Etapa 1: Descoberta

- Definir problema, resultado esperado e criterios de sucesso.
- Classificar risco tecnico e risco de seguranca.
- Definir estrategia de modelo e limite de custo.

## Etapa 2: Planejamento

- Criar sprint com escopo, checklist numerado e evidencias esperadas.
- Definir token budget da sprint.
- Definir testes, validacoes e gate de seguranca.

## Etapa 3: Execucao com AI

- Quebrar tarefa em blocos pequenos.
- Usar prompts orientados a objetivo e contexto minimo.
- Capturar decisoes e deltas relevantes.

## Etapa 4: Validacao

- Rodar teste unitario, integracao e smoke test.
- Validar seguranca e conformidade.
- Revisao humana de mudancas criticas.

## Etapa 5: Publicacao

- Publicar com monitoramento ativo.
- Validar metricas de negocio e engenharia.
- Habilitar plano de rollback rapido.

## Etapa 6: Aprendizado

- Consolidar ganhos, perdas e retrabalho.
- Atualizar memoria institucional.
- Ajustar prompt patterns, controles e templates.

## 6) RACI recomendado

- Product Manager:
  - Prioriza escopo, valor e risco de negocio.
- Tech Lead:
  - Aprova estrategia tecnica e gates de qualidade.
- Engenheiro de Software:
  - Executa implementacao, testes e documentacao.
- Security Champion:
  - Valida controles de dados, segredo e superficie de ataque.
- FinOps Owner:
  - Garante budget, custo por entrega e eficiencia de consumo.
- Platform/DevOps:
  - Mantem observabilidade, automacao e confiabilidade operacional.

## 7) Maturidade do framework

## Nivel 1: Ad hoc

- Uso de AI sem padrao.
- Sem budget, sem metricas e sem rastreabilidade.

## Nivel 2: Repetivel

- Templates e fluxo minimo definidos.
- Primeiros controles de custo e de seguranca.

## Nivel 3: Gerenciado

- Metricas por sprint e gates formais.
- Indicadores estaveis de produtividade e qualidade.

## Nivel 4: Otimizado

- Ajuste continuo de modelo, prompt e automacao.
- Reducao sustentavel de custo por entrega.

## Nivel 5: Escalado

- Operacao multiplos times com padrao unico.
- Benchmark interno por produto e previsibilidade avancada.

## 8) Catalogo de metricas por pilar

| Pilar            | Indicador                        | Meta inicial sugerida     | Frequencia     |
| ---------------- | -------------------------------- | ------------------------- | -------------- |
| Velocidade       | Lead time medio por entrega      | Reducao de 20% em 90 dias | Semanal        |
| FinOps de Tokens | Custo por entrega                | Reducao de 15% em 90 dias | Semanal        |
| Seguranca        | Incidentes relacionados a AI     | Zero incidente critico    | Diario/Semanal |
| Governanca       | Sprints com evidencias completas | 95% ou mais               | Semanal        |
| Visibilidade     | Cobertura de observabilidade AI  | 100% dos fluxos criticos  | Semanal        |

## 9) Checklists executivos de implementacao

## 9.1 Checklist de inicio rapido (30 dias)

- Definir dono do framework por area.
- Definir budget de tokens por time.
- Publicar template unico de sprint.
- Ativar dashboard minimo de custo e uso.
- Definir politica minima de seguranca para prompts.

## 9.2 Checklist de consolidacao (60 dias)

- Conectar custo com throughput por squad.
- Estabelecer gates obrigatorios de seguranca e qualidade.
- Institucionalizar revisao quinzenal de metricas.
- Criar trilha de treinamento interno.

## 9.3 Checklist de escala (90 dias)

- Benchmark entre times por custo x valor entregue.
- Automatizar alertas e acao preventiva de custo.
- Criar playbook de incidentes AI.
- Publicar relatorio executivo mensal de maturidade.

## 10) Playbooks essenciais

## Playbook 1: Explosao de custo de tokens

1. Congelar fluxos nao criticos de alto consumo.
2. Identificar top consumidores em 24 horas.
3. Aplicar limite de contexto e modelo tier mais barato.
4. Revalidar custo por entrega apos 7 dias.

## Playbook 2: Queda de qualidade de output

1. Revisar prompts e entradas de contexto.
2. Rodar suite de regressao focada nos fluxos afetados.
3. Ajustar validadores de saida.
4. Reabrir rollout gradual com monitoramento reforcado.

## Playbook 3: Incidente de seguranca envolvendo AI

1. Conter canal e remover contexto sensivel.
2. Rotacionar credenciais e segredos relacionados.
3. Executar analise de impacto e trilha de auditoria.
4. Corrigir controles e publicar RCA com plano preventivo.

## 11) Framework de comunicacao para palestras

## Estrutura sugerida de palestra

1. Contexto: por que o agora e parceria com AI.
2. Problema: velocidade sem controle gera custo e risco.
3. Solucao: cinco pilares com governanca operacional.
4. Evidencia: metricas antes e depois.
5. Acao: roteiro de implantacao 30-60-90 dias.

## Mensagens fortes para propagar

- AI sem FinOps vira custo invisivel.
- AI sem seguranca vira risco silencioso.
- AI sem governanca vira caos elegante.
- AI com visibilidade vira vantagem competitiva.

## 12) Politica de revisao deste framework

- Revisao mensal dos indicadores e dos controles.
- Revisao trimestral de maturidade e roadmap.
- Atualizacao imediata em caso de incidente critico.

## 13) Como adotar agora neste repositorio

1. Manter sprints e indices alinhados ao manifesto.
2. Medir custo de AI por sprint e por tipo de tarefa.
3. Exigir evidencias de validacao em toda entrega.
4. Expandir dashboard de observabilidade para custo, qualidade e seguranca.
5. Registrar aprendizado operacional de forma continua em memoria institucional.

## 14) Declaracao final

O desenvolvimento em parceria com AI e o novo padrao de engenharia.

Times que combinam velocidade, FinOps, seguranca, governanca e observabilidade entregam mais, com menos risco, menor custo e maior previsibilidade.

Este framework existe para transformar uso de AI em capacidade organizacional duravel.
