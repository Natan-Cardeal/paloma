# Paloma

Plataforma de Relatorios de Sustentabilidade para PMEs brasileiras.

**Produto unico**: Relatorio de Sustentabilidade (3 planos: Essencial | Estruturado | Estrategico)
**Conteudo informacional**: PGRS e Inventario de Carbono GEE (nao vendidos como produto — apenas awareness/SEO)

## Stack

- Next.js 15 (App Router) + TypeScript
- MDX (content in repo)
- Tailwind CSS
- Firebase Hosting + Cloud Functions (SSG + dynamic OG via satori)

## Docs

- `docs/PLANO_CONTEUDO_SEO.pdf` — Plano editorial original v1.0 (26 pags)
- `docs/PLANO_CONTEUDO_SEO_v2.md` — **Plano v2.2 ajustado** (RS produto unico, sem RT, 3 tiers ESG)
- `docs/APRESENTACAO_NEGOCIO_v2.1.md` — Apresentacao de negocio v2.1 (19 secoes)
- `REVIEW.md` — Revisao cascateada por 6 especialistas (50+ recomendacoes)

## Evolucao

| Versao | Status | Descricao |
|---|---|---|
| v1.0 | Superado | Plano original — 26 pags, 48 pecas, 4/mes |
| Review | Completo | 6 especialistas, 50+ findings, 3 bloqueadores criticos |
| v2.0 | Superado | Reescrita completa — 51 pecas, Firebase, funnel CRO, GTM multi-canal |
| v2.1 | Superado | GEE removido como produto (feedback especialista), pricing ajustado para PGRS+RS |
| **v2.2** | **Atual** | Produto unico: RS em 3 tiers (Essencial/Estruturado/Estrategico). PGRS removido como produto. RT eliminado — especialista assina diretamente. RS cobre ESG completo (A+S+G). |

## Pre-requisitos (antes de qualquer codigo)

1. ~~Responsavel Tecnico (CRQ/CREA) contratado~~ **REMOVIDO v2.2** — especialista assina diretamente
2. Modelo de receita definido (hibrido: self-service + done-for-you) ✅ v2.2
3. Dominio registrado + Firebase project configurado
4. Escopo ampliado do RS detalhado (ESG completo: Ambiental + Social + Governanca)
