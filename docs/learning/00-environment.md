# 00 — Ambiente local (inspeção inicial)

Registro do que foi verificado **antes** de qualquer chamada à API Jev.

Data da inspeção: **2026-10-07**

## Workspace

| Item | Valor |
| --- | --- |
| Diretório | `/Users/kleilson/Projects/jev` |
| Conteúdo inicial | vazio (sem arquivos) |
| Repositórios Jev/TypeSafe pré-existentes na conta | nenhum encontrado |

## Ferramentas

| Ferramenta | Resultado |
| --- | --- |
| Git | `git version 2.39.3 (Apple Git-145)` |
| GitHub CLI | `gh version 2.93.0` em `/usr/local/bin/gh` |
| `gh auth status` | autenticado em `github.com` como **KleilsonSantos** |
| Protocolo Git via gh | HTTPS + `gh auth git-credential` |
| Node / npm | não encontrados no PATH inspecionado |
| Docker | não encontrado |
| Java | runtime não localizado |
| Go | não encontrado |
| Homebrew (`brew`) | não encontrado no PATH inspecionado |
| `curl` | `/usr/bin/curl` |

## Python

| Binário | Versão |
| --- | --- |
| `python3` (padrão no PATH) | 3.9.6 |
| `/usr/local/bin/python3.12` | disponível |
| `/usr/local/bin/python3.14` | disponível |

**Implicação:** o SDK oficial `typesafe-sdk` exige Python ≥ 3.10 ([Quick start](https://docs.typesafe.ai/introduction/quickstart)). Para o primeiro Hello Jev, preferir **HTTP + curl** (sem dependência de SDK) **ou** apontar explicitamente para `python3.12` / `python3.14`.

## Git identity

| Item | Valor |
| --- | --- |
| `user.email` (global) | `kdsdesign1@gmail.com` |
| `user.name` (global) | **não configurado** |

Neste laboratório, commits usam identidade explícita no comando de commit (sem alterar `git config`), alinhada ao histórico de outros projetos do usuário (`Kleilson Santos <kdsdesign1@gmail.com>`).

## Conta GitHub

| Item | Valor |
| --- | --- |
| Login | `KleilsonSantos` |
| Nome exibido via API | `kleilsonsantos` |

## O que ainda falta para executar Jev

1. API key TypeSafe (`TYPESAFE_API_KEY`) — criar no dashboard (ver Quick start).
2. Confirmar se há crédito / free tier disponível na conta (**Não confirmado** nas docs públicas consultadas).
3. Executar o menor request e registrar evidência em `docs/experiments/`.

## Relação com outros projetos locais

No mesmo diretório `Projects/` existem, entre outros:

- `ai-operating-system`
- `aios-companion`
- `cloud-event-lab`
- `mcp-rag-lab`

**Integração com AIOS ou outros projetos:** fora de escopo até o laboratório validar fundamentos (ver roadmap, níveis 7–8).
