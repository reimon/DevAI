# CHANGELOG.md - Histórico do Manifesto

Histórico de principais atualizações e versões do manifesto de governança.

## [v1.0] - 2026-03-18

### Adicionado

- **Manifesto base** com 18 regras obrigatórias
- **Estrutura de sprints** com 16 seções mandatórias
- **Governança de MEMORY.md** com 6 campos essenciais
- **Planos de execução** (.github/prompts/) como padrão
- **Templates reutilizáveis** para sprint, memória e índices
- **Guia INSTALL.md** com 6 fases de setup
- **FAQ.md** com troubleshooting comum

### Estrutura Inicial

```
framework-agora/
├── docs/
│   ├── MANIFESTO-DEV-IA.md       (130 linhas)
│   ├── MEMORY.md                 (template)
│   └── SPRINTS-MVP.md            (exemplo completo)
├── .github/prompts/
│   └── plan-setup-governanca.prompt.md (115 linhas)
├── templates/
│   ├── SPRINTS-CHECKLIST-TEMPLATE.md
│   └── sprint-template.md
├── README.md
├── INSTALL.md
├── CHANGELOG.md (este arquivo)
├── LICENSE
└── FAQ.md
```

### Fases Documentadas

1. ✅ Manifesto de governança (Sprint 15-27 da Health Platform)
2. ✅ Memória institucional versionada (docs/MEMORY.md)
3. ✅ Planos de execução do agente (.github/prompts/)
4. ✅ Documentação de setup inicial
5. ✅ Templates de sprint e índices
6. ✅ Guia de instalação passo-a-passo
7. ✅ FAQ de troubleshooting

## Princípios Principais

### Sprint-Primeiro Obrigatório

Nenhuma mudança técnica inicia fora de sprint. Toda ação deve estar documentada em arquivo de sprint **antes** da execução.

### Manifesto como Fonte de Verdade

`docs/MANIFESTO-DEV-IA.md` é a fonte canônica de todas as regras de governança.

### Memória Versionada

`docs/MEMORY.md` é o arquivo único de memória institucional, versionado em Git.

### Transparência Total

Todas as sprints, decisões e evidências ficam registradas e rastreáveis permanentemente.

## Regras Imutáveis

As seguintes regras não mudam entre versões:

1. Toda mudança deve estar em sprint **antes** da execução
2. Manifesto é fonte de verdade
3. Sprints devem ter 16 seções na ordem correta
4. MEMORY.md é o arquivo único de memória
5. Nenhum segredo em arquivos de documentação
6. Datas em formato ISO `YYYY-MM-DD`
7. Evidência obrigatória para cada ação concluída
8. Commit obrigatório após sprint concluída

## Como Contribuir

Para sugerir melhorias ao manifesto:

1. Abra issue com tag `[improvement]` ou `[bug]`
2. Descreva claramente a necessidade
3. Forneça exemplo de uso
4. Aguarde feedback e validação
5. Crie PR com alterações propostas

## Roadmap Futuro

Potenciais adições (não confirmadas):

- [ ] Integração com ferramentas de rastreamento (Jira, Linear)
- [ ] Script de validação automática de sprints
- [ ] Dashboard de portfolio de sprints
- [ ] Integração com GitHub Actions para CI/CD
- [ ] Suporte para multi-idioma

## Versões Anteriores

Nenhuma versão anterior — v1.0 é a primeira.

## Conclusões

Este manifesto foi desenvolvido na prática, através de 27 sprints da Health Platform, validando:

- Rastreabilidade total entre commits e sprints
- Redução de ambiguidade em handoffs entre agentes
- Economia de contexto para LLMs
- Reusabilidade de padrões entre projetos
- Escalabilidade para múltiplas aplicações

A estrutura é simples, clara e funciona em Git sem ferramentas externas.
