# Roadmap do laboratório

Evolução planejada. Só avançamos de nível quando o critério de entendimento estiver claro.

## Nível 1 — Repository Bootstrap

```text
Workspace → Git → GitHub CLI → Repositório → README → Issue inicial
```

**Critério:** repo público versionado, docs base, Issue LAB-001.

**Status:** concluído em 2026-10-07 — Issue [#1](https://github.com/KleilsonSantos/jev-learning-lab/issues/1) fechada.

## Nível 2 — Hello Jev

```text
API key → POST /v1/systemone → observar answers → documentar evidência
```

**Critério:** “Consigo executar Jev e observar claramente o que ele está fazendo?”

Preferência inicial: **HTTP + curl** (menor superfície). SDK Python só depois, com `python3.12+`.

## Nível 3 — Conceitos fundamentais

State, Noul, Choice, Score, confidence — um experimento por conceito quando útil.

## Nível 4 — Configuração

Alterar `instructions` / `criteria` / `state` e comparar resultados (A/B controlado).

## Nível 5 — Experimentos

Séries EXP-NNN com hipóteses, controle e conclusão.

## Nível 6 — Integração simples

Uma aplicação mínima (CLI ou script) que **ramifica** com base nas answers.

## Nível 7 — Avaliação arquitetural

Benefícios, limitações, custo, lock-in, observabilidade, rollback.

## Nível 8 — Integração com projetos reais

Somente após Nível 7. Candidatos futuros (ex.: AIOS) exigem análise de aderência explícita — **não agora**.

## Milestones no GitHub

Milestones formais (Fundamentals / Experiments / Integration / Evaluation) serão criados quando houver escopo e Issues suficientes para justificá-los. No bootstrap: **ainda não**.

## Issues previstas (esqueleto)

| ID | Título | Nível |
| --- | --- | --- |
| LAB-001 | Bootstrap do workspace e repositório | 1 |
| LAB-002 | Primeira chamada funcional (Hello Jev) | 2 |
| LAB-003 | Conceitos: state + Noul | 3 |
| LAB-004 | Choice e Score no mesmo request | 3 |

Issues além de LAB-001 só nascem quando formos executá-las de fato (YAGNI de processo).
