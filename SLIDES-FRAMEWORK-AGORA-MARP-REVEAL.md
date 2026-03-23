<!--
marp: true
theme: default
paginate: true
size: 16:9
title: Framework Agora - Desenvolvimento em Parceria com AI
description: Velocidade, FinOps de tokens, seguranca, governanca e monitoramento para escalar engenharia com AI.
-->

# Framework Agora

## Desenvolvimento em Parceria com AI

Velocidade com controle de custo, risco e qualidade.

**Palestra base:** 30-45 minutos

---

# Agenda

1. O agora da engenharia com AI
2. O problema que quase ninguem mede
3. Os 5 pilares do Framework Agora
4. Modelo operacional ponta a ponta
5. Plano 30-60-90 dias
6. KPIs executivos e CTA

---

# O Agora

AI ja esta no fluxo real de desenvolvimento.

A pergunta nao e mais:

- "Vamos usar AI?"

A pergunta certa e:

- "Como operamos AI com previsibilidade de custo, qualidade e seguranca?"

---

# O Problema Real

Sem modelo operacional, a aceleracao inicial vira:

- retrabalho crescente
- custo de tokens invisivel
- risco tecnico e de seguranca
- baixa rastreabilidade de decisoes

---

# Tese Central

Times que combinam **velocidade + FinOps + seguranca + governanca + observabilidade**

entregam mais, com menor risco e custo controlado.

---

# Os 5 Pilares

1. Velocidade de desenvolvimento
2. FinOps de tokens
3. Seguranca
4. Governanca
5. Visibilidade e monitoramento

---

# Pilar 1: Velocidade

## Objetivo

Aumentar throughput sem degradar qualidade.

## Praticas-chave

- ciclos curtos de entrega
- escopo e fora de escopo explicitos
- definicao de pronto com validacao
- registro de decisoes tecnicas no momento da mudanca

---

# Pilar 1: Antipadroes

Evitar:

- prompt longo sem objetivo claro
- reescrita total quando bastava delta
- codegen sem gate de teste
- entrega grande sem checkpoints

---

# Pilar 2: FinOps de Tokens

## Premissa

Token e custo variavel de engenharia.

## Controles minimos

- budget por time e produto
- guardrails por fluxo
- tiers de modelo por complexidade
- contexto minimo necessario

---

# Pilar 2: Indicadores

Monitorar:

- custo por funcionalidade entregue
- tokens por historia concluida
- taxa de resolucao no primeiro ciclo
- custo de retrabalho por erro de geracao

**Meta inicial sugerida:** reduzir custo por entrega em 15% em 90 dias.

---

# Pilar 3: Seguranca

## Riscos especificos de AI

- prompt injection
- exfiltracao de dados
- output com falsa confianca
- geracao de codigo inseguro

## Controles minimos

- classificacao de dados
- zero segredo em prompt/log
- validacao de output antes de producao
- auditoria de contexto e decisao

---

# Pilar 4: Governanca

## Sem padrao, cada sprint vira uma linguagem diferente

Padronizar:

- estrutura de sprint
- status e criterio de transicao
- checklist numerado com evidencia
- commits e pendencias explicitas

**Referencia operacional:** ../docs/MANIFESTO-DEV-IA.md

---

# Pilar 5: Visibilidade e Monitoramento

## O que monitorar

- custo, volume e latencia por fluxo AI
- taxa de falha por etapa
- aceite, ajuste e descarte de output
- regressao apos release assistido por AI

## Sem observabilidade nao existe melhoria continua

---

# Modelo Operacional (E2E)

1. Descoberta
2. Planejamento
3. Execucao com AI
4. Validacao
5. Publicacao
6. Aprendizado

Cada etapa com dono, gate e evidencia.

---

# Descoberta e Planejamento

## Descoberta

- problema
- resultado esperado
- risco tecnico e de seguranca

## Planejamento

- sprint com checklist numerado
- budget de tokens da sprint
- criterios de validacao e release

---

# Execucao e Validacao

## Execucao

- tarefas pequenas
- contexto minimo
- deltas objetivos

## Validacao

- testes automatizados
- revisao humana de mudancas criticas
- checagens de seguranca e conformidade

---

# Publicacao e Aprendizado

## Publicacao

- monitoramento ativo
- rollback preparado
- observacao de KPIs

## Aprendizado

- consolidar ganhos e perdas
- ajustar prompts, controles e templates
- atualizar memoria institucional

---

# Maturidade em 5 Niveis

1. Ad hoc
2. Repetivel
3. Gerenciado
4. Otimizado
5. Escalado

Nao pule etapas: escala sem base cria caos sofisticado.

---

# KPIs do Conselho / Diretoria

- lead time medio por entrega
- custo por entrega assistida por AI
- incidentes de seguranca relacionados a AI
- percentual de sprints com evidencia completa
- cobertura de observabilidade dos fluxos criticos

---

# Plano 30-60-90 Dias

## 30 dias

- definir owners por pilar
- estabelecer budget de tokens
- padronizar sprint e evidencias

## 60 dias

- conectar custo com throughput
- formalizar gates de seguranca
- ritual quinzenal de metricas

## 90 dias

- benchmark entre squads
- alertas automativos de custo e qualidade
- relatorio executivo mensal de maturidade

---

# Playbook 1: Explosao de Custo

1. congelar fluxos nao criticos de alto consumo
2. identificar top consumidores em 24h
3. reduzir contexto e tier de modelo
4. revalidar custo por entrega em 7 dias

---

# Playbook 2: Queda de Qualidade

1. revisar prompt e contexto
2. regressao focada nos fluxos afetados
3. reforcar validadores de saida
4. retomar rollout gradual com monitoramento

---

# Playbook 3: Incidente de Seguranca

1. conter canal e remover contexto sensivel
2. rotacionar segredos e credenciais
3. executar analise de impacto e auditoria
4. publicar RCA com acao preventiva

---

# Caso Pratico (Exemplo)

## Antes

- entrega rapida sem governanca
- custo crescente sem previsibilidade
- regressao frequente

## Depois

- lead time: -20%
- custo por entrega: -15%
- sprints com evidencia: +95%

---

# Mensagens-Chave

- AI sem FinOps vira custo invisivel.
- AI sem seguranca vira risco silencioso.
- AI sem governanca vira caos elegante.
- AI com visibilidade vira vantagem competitiva.

---

# Chamada para Acao

Escolha um produto piloto.

Implante o framework em 30 dias.

Publique a primeira curva de aprendizado com:

- custo
- qualidade
- seguranca
- velocidade

---

# Materiais de Apoio

- FRAMEWORK-DEV-AI-FINOPS.md
- FRAMEWORK-DEV-AI-FINOPS.html
- ROTEIRO-PALESTRA-FRAMEWORK-AGORA-30-45MIN.md
- ONE-PAGER-EXECUTIVO-CONSELHO-AI.md

---

# Obrigado

Framework Agora

Desenvolvimento em parceria com AI com escala, seguranca e FinOps.
