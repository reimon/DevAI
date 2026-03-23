# Roteiro de Palestra - Framework Agora (30-45 min)

## 1) Objetivo da palestra

Apresentar um framework pratico para desenvolvimento em parceria com AI, com foco em cinco pilares:

- Velocidade com qualidade.
- FinOps de tokens.
- Seguranca.
- Governanca.
- Visibilidade e monitoramento.

Resultado esperado:

A audiencia sai com um plano de implantacao em 30-60-90 dias e um modelo de operacao replicavel.

## 2) Publico-alvo

- CTOs, Heads, Tech Leads, Engenheiros, DevOps, FinOps e Security.
- Empresas que ja usam AI em engenharia, mas sem modelo de controle.

## 3) Formatos de tempo

## Versao A - 30 minutos

- 0-3 min: abertura e contexto.
- 3-8 min: problema real do mercado.
- 8-18 min: os cinco pilares.
- 18-24 min: modelo operacional 30-60-90.
- 24-28 min: caso pratico e metricas.
- 28-30 min: fechamento e CTA.

## Versao B - 45 minutos

- 0-5 min: abertura com narrativa.
- 5-12 min: problema, anti-padroes e impacto.
- 12-27 min: cinco pilares com exemplos tecnicos.
- 27-36 min: modelo operacional + playbooks.
- 36-41 min: estudo de caso e metricas.
- 41-45 min: Q&A + chamada para adocao.

## 4) Estrutura de slides sugerida

### Slide 1 - Titulo

Mensagem:

- Desenvolvimento em parceria com AI: da euforia para a operacao madura.

Fala sugerida (30s):

"AI ja esta no fluxo real de engenharia. A pergunta nao e se vamos usar. E se vamos operar com disciplina suficiente para escalar sem caos."

### Slide 2 - O agora

Mensagem:

- AI acelerou a producao de codigo, mas tambem acelerou retrabalho, custo invisivel e risco operacional.

Dado que pode citar:

- Sem governanca, o ganho inicial de velocidade degrada em 2-3 ciclos de sprint.

### Slide 3 - Problema de fundo

Mensagem:

- Velocidade sem controle gera tres passivos:
  - Custo variavel imprevisivel.
  - Divida tecnica acelerada.
  - Risco de seguranca e compliance.

### Slide 4 - Tese do framework

Mensagem:

- Cinco pilares operando juntos criam vantagem competitiva sustentavel.

Frase-chave:

- AI sem FinOps vira custo invisivel.
- AI sem seguranca vira risco silencioso.
- AI sem governanca vira caos elegante.

### Slide 5 - Pilar 1: Velocidade

Mensagem:

- Entrega rapida exige ciclos curtos, escopo claro e validacao continua.

Checklist de fala:

- Sprint com escopo e fora de escopo.
- Delta update em vez de reescrita total.
- Gate de teste e definicao de pronto.

### Slide 6 - Pilar 2: FinOps de Tokens

Mensagem:

- Token e custo variavel de engenharia. Trate como qualquer outro custo de cloud.

Checklist de fala:

- Budget por time.
- Guardrails por fluxo.
- Tiers de modelo por complexidade.
- KPI de custo por entrega.

### Slide 7 - Pilar 3: Seguranca

Mensagem:

- O risco mais caro e o que nao aparece no dashboard.

Checklist de fala:

- Classificacao de dados antes de prompt.
- Zero segredo em contexto.
- Validacao de output e auditoria de decisoes.

### Slide 8 - Pilar 4: Governanca

Mensagem:

- Sem padrao, cada sprint vira uma linguagem diferente.

Checklist de fala:

- Estrutura unica de sprint.
- Status padronizado.
- Evidencia minima por acao concluida.
- Pendencias explicitadas para proxima sprint.

### Slide 9 - Pilar 5: Visibilidade e Monitoramento

Mensagem:

- O que nao e observado nao pode ser otimizado.

Checklist de fala:

- Custo, latencia, falha e aceite de output.
- Alertas de consumo anomalo.
- Dashboard executivo por custo x valor.

### Slide 10 - Modelo operacional ponta a ponta

Mensagem:

- Descoberta -> Planejamento -> Execucao -> Validacao -> Publicacao -> Aprendizado.

Foco:

- Cada etapa tem dono, metrica e evidencia.

### Slide 11 - Maturidade em 5 niveis

Mensagem:

- Ad hoc -> Repetivel -> Gerenciado -> Otimizado -> Escalado.

Fala:

- Nao tente pular etapa. Escala exige consistencia antes de sofisticacao.

### Slide 12 - Metricas que importam

Mensagem:

- Lead time.
- Custo por entrega.
- Incidentes de seguranca.
- Sprints com evidencia completa.
- Cobertura de observabilidade AI.

### Slide 13 - Plano 30-60-90 dias

Mensagem:

- 30 dias: baseline e donos.
- 60 dias: gates e rituais.
- 90 dias: escala e benchmark entre squads.

### Slide 14 - Playbooks de crise

Mensagem:

- Explosao de custo de tokens.
- Queda de qualidade de output.
- Incidente de seguranca envolvendo AI.

Objetivo:

- Mostrar preparo operacional, nao apenas estrategia.

### Slide 15 - Caso pratico

Modelo de narrativa:

- Antes: output rapido, retrabalho alto e custo sem previsibilidade.
- Depois: backlog mais curto, custo controlado, menos regressao.

Numeros exemplo:

- -20% lead time.
- -15% custo por entrega.
- +95% sprints com evidencias completas.

### Slide 16 - Fechamento

Mensagem final:

- Desenvolvimento com AI e o novo padrao.
- Diferencial real: operar AI com metodo, seguranca e disciplina financeira.

CTA:

- "Escolha um produto, implante em 30 dias e publique sua primeira curva de aprendizado."

## 5) Script de abertura (2 minutos)

"Nos ultimos meses, a engenharia ganhou velocidade com AI. So que junto com a velocidade veio um novo tipo de complexidade: custo variavel de tokens, risco operacional e uma falsa sensacao de produtividade. Este talk mostra como transformar uso de AI em capacidade de engenharia sustentavel. Nao com promessas vagas, mas com um framework operacional de cinco pilares: velocidade, FinOps de tokens, seguranca, governanca e visibilidade. Se voce sair daqui com um plano de 30-60-90 dias, o objetivo foi cumprido."

## 6) Script de fechamento (1-2 minutos)

"A parceria com AI nao e mais experimento de borda. E o centro da engenharia moderna. O time que vai liderar o mercado nao e o que gera mais codigo. E o que combina velocidade com controle de custo, seguranca por design, governanca objetiva e monitoramento continuo. Comece pequeno, mas comece com metodo."

## 7) Perguntas para engajar a audiencia

- Quantos aqui medem custo de tokens por entrega, e nao apenas por mes?
- Quem ja teve regressao por output gerado sem gate de validacao?
- Seu time tem um playbook claro para incidente de seguranca envolvendo AI?

## 8) Q&A - perguntas provaveis e respostas curtas

### P: Isso aumenta burocracia?

R: Aumenta clareza, nao burocracia. O framework reduz retrabalho e acelera decisoes.

### P: Como justificar investimento em monitoramento?

R: Sem observabilidade, o custo de erro e invisivel. O investimento se paga com reducao de desperdicio e incidente.

### P: Qual o primeiro passo realista?

R: Definir owners por pilar, ativar budget de tokens por time e padronizar sprint em 30 dias.

## 9) Material de apoio para divulgar depois da palestra

- Framework completo em markdown: [FRAMEWORK-DEV-AI-FINOPS.md](FRAMEWORK-DEV-AI-FINOPS.md)
- Versao web para publicacao direta: [FRAMEWORK-DEV-AI-FINOPS.html](FRAMEWORK-DEV-AI-FINOPS.html)
- Diretriz operacional do repositorio: [../docs/MANIFESTO-DEV-IA.md](../docs/MANIFESTO-DEV-IA.md)

## 10) Checklist de preparacao do palestrante

### Antes (D-7 a D-1)

- Ajustar exemplos para o contexto da audiencia.
- Separar 1 caso real com dados simples de antes/depois.
- Ensaiar versao de 30 min e versao de 45 min.

### No dia

- Testar projetor e resolucao.
- Levar backup PDF dos slides.
- Deixar QR code para materiais finais.

### Depois

- Publicar materiais em um unico link.
- Coletar feedback em 3 perguntas objetivas.
- Atualizar o framework com aprendizados da sessao.
