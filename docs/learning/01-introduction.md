# 01 — Introdução ao Jev (conceitos antes da prática)

## O que vamos fazer?

Fixar o mapa mental de **o que Jev é e o que Jev não é**, com base apenas na documentação oficial TypeSafe, antes de escrever código de integração.

## Por que?

Sem esse mapa, é comum tratar Jev como “mais um LLM”. Isso gera expectativas erradas (chat, geração de código, prompt engineering clássico) e experimentos ruins.

## Conceito

Fontes: [Introduction](https://docs.typesafe.ai/introduction), [System One](https://docs.typesafe.ai/concepts/system-one), [Jev with coding agents](https://docs.typesafe.ai/introduction/coding-agents).

```text
state  +  questions tipadas
            ↓
     um request HTTP
            ↓
   answers tipadas + probabilities
   (+ confidence em Choice/Score)
            ↓
      seu código decide
   (branch, sort, route, escalate)
```

### Três primitivas

| Primitiva | Objetivo | Retorno principal |
| --- | --- | --- |
| **Noul** | Sim/não (probabilidade de “sim”) | `noul` ∈ [0, 1] |
| **Choice** | Escolher 1 opção entre N | `choice` + `probabilities` + `confidence` |
| **Score** | Posicionar em uma régua ordenada | `score` (pode ser decimal) + `probabilities` + `confidence` |

Várias perguntas podem ir no **mesmo** request e são avaliadas em paralelo contra o mesmo `state`.

### Diferença em relação a um LLM

| LLM típico | Jev (System One) |
| --- | --- |
| Gera texto para humanos | Devolve decisões tipadas para software |
| Prompt aberto, parsing frágil de JSON | Schema/tipos definidos na pergunta |
| Temperatura / prose | Probabilidades calibradas para decisão |

Calibração é medida em **grupos** de predições; **não** garante que uma resposta individual esteja correta (doc oficial).

## Analogia

Pense em um **árbitro de decisões rápidas**, não em um escritor.

Você entrega o dossiê (`state`) e um checklist fechado (`questions`). O árbitro marca opções e níveis de certeza. **Você** (o código) decide o que fazer com isso — liberar, escalar, rotear, pedir revisão humana.

## Como (ainda sem implementar)

Menor fluxo oficial ([Quick start](https://docs.typesafe.ai/introduction/quickstart)):

1. Obter `TYPESAFE_API_KEY`.
2. `POST https://api.typesafe.ai/v1/systemone`
3. Body mínimo: `state`, `model` (`jev-latest`), `questions` com pelo menos uma pergunta.
4. Ler `answers` pela mesma chave que você escolheu.

Exemplo mínimo (documentação oficial — Noul):

```json
{
  "state": "Hi, I've been trying to connect my Stripe account for 3 days and the integration keeps failing. I'm losing sales. Please help ASAP.",
  "model": "jev-latest",
  "questions": {
    "urgency": {
      "type": "noul",
      "instructions": "Does this message express urgency?"
    }
  }
}
```

## Experimento (próximo nível)

No Nível 2, executar **exatamente** esse formato (ou equivalente de uma pergunta) e registrar:

- comando;
- status HTTP;
- trecho relevante da resposta;
- modelo efetivo retornado em `model`;
- o que foi aprendido.

Arquivo previsto: `docs/experiments/EXP-001-first-run.md`

## Critério de sucesso desta página

Conseguir explicar, sem consultar o chat:

1. O que entra no request.
2. O que sai na response.
3. Por que Jev não substitui o LLM do Cursor/Claude Code.
4. Qual endpoint e variável de ambiente oficiais.

## Limitações conscientes

- Ainda **não** houve chamada real a partir deste workspace.
- Preços, quotas da conta e free tier: ver Models / dashboard — detalhes de billing da *sua* conta = **Não confirmado** até o primeiro request autenticado.
- Entrada multimídia (imagem/áudio/vídeo): não suportada “ainda” (doc System One).

## Próximo passo

Criar e executar **LAB-002 / EXP-001**: Hello Jev via `curl` + uma Noul.
