# Fontes oficiais e regras de evidência

## Fonte canônica

Prioridade absoluta para afirmações sobre Jev / TypeSafe:

| Recurso | URL |
| --- | --- |
| Índice para agentes (`llms.txt`) | https://docs.typesafe.ai/llms.txt |
| Introduction | https://docs.typesafe.ai/introduction |
| Quick start | https://docs.typesafe.ai/introduction/quickstart |
| System One | https://docs.typesafe.ai/concepts/system-one |
| API reference | https://docs.typesafe.ai/api |
| Models | https://docs.typesafe.ai/models |
| Python SDK | https://docs.typesafe.ai/sdk/python |
| Jev com coding agents | https://docs.typesafe.ai/introduction/coding-agents |
| Endpoint de avaliação | `POST https://api.typesafe.ai/v1/systemone` |
| Listagem de modelos | `GET https://api.typesafe.ai/v1/models` |

Consultado em: **2026-10-07** (datas de captura deste laboratório).

## O que está confirmado (docs oficiais)

- Jev é o modelo flagship System One da TypeSafe.
- Entrada: `state` + `questions`; saída: `answers` tipadas + `usage`.
- Três primitivas: Noul, Choice, Score.
- Alias `jev-latest` aponta para `jev-1.13.0` (no momento da consulta a Models).
- SDK Python oficial: `typesafe-sdk`, requer **Python ≥ 3.10**.
- Variável de ambiente do SDK: `TYPESAFE_API_KEY`.
- Jev **não** substitui o LLM de um coding agent; é usado **dentro** de código que o agent ajuda a escrever.

## Divergência registrada (não usar como canônica)

Durante a pesquisa inicial, também apareceu **https://jev-ai.org/docs/** com:

- host diferente (`jev-ai.org` vs `api.typesafe.ai`);
- path diferente (`/api/v1/systemone/` vs `/v1/systemone`);
- formato de chave descrito de forma diferente (`sk-glm5-` vs fluxo do dashboard TypeSafe).

**Decisão deste laboratório:** seguir **somente** `docs.typesafe.ai` e `api.typesafe.ai`, salvo evidência futura de que `jev-ai.org` seja o mesmo produto sob outro domínio (hoje: **não confirmado**).

Outras menções secundárias (ex.: jevwiki.ai, blogs) só entram como apoio se forem rastreáveis até a documentação TypeSafe.

## Regras anti-alucinação

Antes de afirmar API, CLI, comando, versão, configuração ou limite:

1. confirmar em fonte da tabela canônica;
2. se não confirmar, marcar explicitamente **Não confirmado** ou **Hipótese a validar**;
3. não tratar exemplo de blog/fórum como prova se houver doc oficial conflitante.

## Documentação vs evidência

| Tipo | Significado |
| --- | --- |
| Documentação oficial | O que *deveria* acontecer |
| Experimento (`docs/experiments/`) | O que *realmente* aconteceu localmente |
| Conclusão | O que *confirmamos* neste ambiente |
