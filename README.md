# jev-learning-lab

Laboratório prático e progressivo para aprender **Jev** (modelo System One da [TypeSafe AI](https://docs.typesafe.ai/introduction)).

> **Não é um projeto de produção.** É uma bancada: setup → execução → observação → documentação → versionamento → evolução.

## Analogia

Imagine uma bancada de laboratório, não uma fábrica.

```text
ligar o equipamento
      ↓
entender os componentes
      ↓
executar um experimento
      ↓
observar o resultado
      ↓
registrar
      ↓
alterar uma variável
      ↓
observar novamente
```

## O que é Jev (resumo confirmado)

Jev **não** é um LLM de chat ou de geração de código.

Ele avalia um **state** (texto ou JSON) contra **perguntas tipadas** e devolve respostas estruturadas que o seu código pode consumir diretamente:

| Tipo | Pergunta típica | Retorno |
| --- | --- | --- |
| **Noul** | Isto é verdadeiro? | probabilidade 0–1 |
| **Choice** | Qual opção? | opção + distribuição |
| **Score** | Em que nível da régua? | score + distribuição |

Fonte oficial: [Introduction](https://docs.typesafe.ai/introduction) · [System One](https://docs.typesafe.ai/concepts/system-one) · [Quick start](https://docs.typesafe.ai/introduction/quickstart)

## Princípio norteador

```text
📚 Aprender → 🧪 Experimentar → 🔎 Observar → ✅ Validar
→ 📝 Documentar → 🐙 Versionar → 📌 Issue → 🚀 Evoluir
```

Prioridade: **clareza → simplicidade → evidência → experimentação → documentação → versionamento**.

## Status atual

| Nível | Descrição | Status |
| --- | --- | --- |
| 1 | Repository Bootstrap | concluído ([#1](https://github.com/KleilsonSantos/jev-learning-lab/issues/1)) |
| 2 | Hello Jev (menor chamada funcional) | pendente |
| 3 | Conceitos fundamentais | pendente |
| 4+ | Configuração, experimentos, integração | futuro |

Detalhes: [`docs/roadmap.md`](docs/roadmap.md)

## Estrutura

```text
README.md
.env.example
docs/
├── sources.md
├── roadmap.md
├── learning/
│   ├── 00-environment.md
│   └── 01-introduction.md
├── experiments/          # EXP-NNN após execuções reais
└── decisions/            # ADRs quando houver decisão real
```

## Pré-requisitos (Nível 1)

Já validados neste workspace:

- Git
- GitHub CLI (`gh`) autenticado
- Conta GitHub

Para o **Nível 2** (primeira chamada à API) será necessário:

1. Conta TypeSafe e API key (`TYPESAFE_API_KEY`) — [Quick start](https://docs.typesafe.ai/introduction/quickstart)
2. `curl` **ou** Python ≥ 3.10 com `typesafe-sdk`

**Não confirmado nesta etapa:** existência de créditos gratuitos / free tier. A documentação oficial descreve cobrança por token de entrada; output é gratuito ([Models](https://docs.typesafe.ai/models)).

## Fontes oficiais

Lista canônica e notas de divergência: [`docs/sources.md`](docs/sources.md)

## Uso de IA neste projeto

Este laboratório também serve à prática de AI Engineering. Quando IA for usada para pesquisa, código ou docs, registrar no experimento ou na Issue correspondente: gerar → revisar → executar → testar → confirmar → documentar → commit.

## Próximo passo

Issue **[LAB-002]** — menor exemplo funcional via HTTP (`POST /v1/systemone`) com uma única pergunta **Noul**, depois documentar evidência em `docs/experiments/`.
