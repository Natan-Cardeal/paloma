# Revisao Cascateada — Plano de Conteudo SEO

**Data**: 2026-03-30
**Documento revisado**: PLANO_CONTEUDO_SEO v1.0 Final (26 paginas)
**Metodologia**: 6 agentes especialistas em paralelo, revisao cruzada

---

## Painel de Especialistas

| # | Especialista | Foco | Score Geral |
|---|---|---|---|
| 1 | SEO Tecnico Senior | URL architecture, schema, CWV, crawl, cannibalization | 5.6/10 |
| 2 | Content Strategist | Topic clusters, funnel, calendar, gaps, differentiation | 7/10 (editorial forte, gaps criticos) |
| 3 | Regulatorio Ambiental BR | Leis, resolucoes, credenciamento, scope accuracy | 4/10 (riscos legais criticos) |
| 4 | CRO / Conversao | CTAs, lead capture, funnel, pricing UX, social proof | 3/10 (infraestrutura de conversao inexistente) |
| 5 | Arquiteto Next.js | Stack, rendering, CMS, hosting, CI/CD, performance | 7/10 (boas bases, decisoes-chave pendentes) |
| 6 | Growth Strategist B2B | Unit economics, channels, pricing, partnerships, PLG | 5/10 (plano editorial excelente, GTM fragil) |

---

## DESCOBERTAS CRITICAS UNIFICADAS

### BLOCO 1 — Viabilidade do Negocio (Pre-requisitos antes de qualquer conteudo)

#### B1.1 LICENCIAMENTO PROFISSIONAL (Regulatorio + Growth)
**O plano inteiro depende de um RT (Responsavel Tecnico) que nao existe.**

PGRS, PGRSS e PGRCC exigem assinatura com ART (Anotacao de Responsabilidade Tecnica) de profissional habilitado (CRQ, CREA, CRBio, CRF, CRMV conforme o tipo). Sem isso:
- A plataforma nao pode legalmente entregar documentos assinados
- Configura exercicio ilegal da profissao (Dec-Lei 3.688/1941, Art. 47)
- Claims de E-E-A-T com credenciais falsas destroem confianca

**Acao**: Contratar ou firmar parceria com RT antes de publicar qualquer conteudo. Opcoes:
1. Retainer mensal com profissional CRQ/CREA (~R$2.000-3.000/mes)
2. Fee por documento (R$200-500/ART) — viavel no inicio
3. Reposicionar como "plataforma de geracao" onde cliente traz seu proprio RT (reduz value prop)

#### B1.2 MODELO DE RECEITA AMBIGUO (CRO + Growth)
CTAs misturam "Solicitar orcamento" (servico) com "Ver precos" (plataforma self-service). Sao modelos de conversao fundamentalmente diferentes.

**Acao**: Definir ANTES do lancamento:
- **Self-service**: preco fixo, checkout online, "Contratar agora"
- **Done-for-you**: "Fale com especialista", WhatsApp, proposta
- **Hibrido** (recomendado): duas lanes explicitas na pagina de precos

#### B1.3 UNIT ECONOMICS NAO FECHAM (Growth)
Com R$790/PGRS, content-only, os primeiros 6 meses geram ~R$10.000 total (~R$1.667/mes). Insustentavel para operacao solo.

**Acao**: Implementar multi-channel desde Dia 1:
- Outbound para contadores (Channel #1, nao #3)
- Google Ads R$500-1.000/mes em termos de alta intencao
- Listagem em marketplaces (GetNinjas, Workana) — custo zero
- Pricing tiered: Standard/Express/Urgente (ver Secao Pricing abaixo)

---

### BLOCO 2 — Falhas Estruturais do Plano de Conteudo

#### B2.1 PILAR GEE AUSENTE DO CALENDARIO (SEO + Content)
O pilar "Guia Completo do Inventario de Carbono GEE" NUNCA aparece no calendario. Satelites GEE comecam no Mes 2 sem hub page. Isso quebra toda a arquitetura de topic cluster do GEE.

**Acao**: Agendar pilar GEE no Mes 1 (como 5a peca) ou Mes 2 Semana 1. NUNCA publicar satelite antes do pilar existir.

#### B2.2 DEFICIT SEVERO DE TOFU (Content)
~70% do conteudo e MOFU/BOFU. Assume que o leitor ja sabe que precisa de PGRS/GEE/RS. Ignora o enorme pool de PMEs que nem sabe que tem obrigacao de compliance.

**Acao**: Adicionar 4-6 artigos TOFU nos Meses 3-6:
- "O que e ESG e Por Que Sua Empresa Precisa se Preocupar em 2025"
- "5 Multas Ambientais que PMEs Recebem Sem Saber"
- "Sustentabilidade Empresarial: Modismo ou Obrigacao Legal?"
- "Seu Contador Deveria Ter Te Avisado Sobre Isso"

#### B2.3 INFRAESTRUTURA DE CONVERSAO INEXISTENTE (CRO)
O plano trata o site como plataforma de publicacao, nao maquina de conversao. Faltam:
- **Zero lead magnets** (70%+ do trafego sai sem captura)
- **Zero nurture sequences** (email nao existe alem de "newsletter")
- **Zero social proof** (nenhum depoimento, case study, logo, NPS)
- **Zero WhatsApp integration** (canal #1 de conversao B2B no Brasil)
- **Zero forms definidos** (o que acontece apos "Solicitar orcamento"?)

**Acao**: Construir ANTES do primeiro artigo:
1. Lead magnet por cluster (checklist PGRS, planilha GEE, template RS)
2. WhatsApp floating button em todas as paginas
3. 3 email nurture sequences (1 por produto, 5-7 emails)
4. Social proof badges (CRQ, metodologia GHG Protocol)
5. Formulario de intake (max 5 campos)

#### B2.4 CONTEUDO REGULATORIO POR ESTADO AUSENTE (Regulatorio + Content)
O plano trata o Brasil como mercado unico. CETESB (SP), FEAM (MG), INEA (RJ), FEPAM (RS), IAT (PR) tem requisitos DIFERENTES para PGRS. Um PGRS generico federal pode nao ser aceito em SP.

**Acao**: Adicionar 5 satelites estaduais ao cluster PGRS (Meses 4-10):
- `/pgrs/pgrs-cetesb-sao-paulo/`
- `/pgrs/pgrs-feam-minas-gerais/`
- `/pgrs/pgrs-inea-rio-de-janeiro/`
- `/pgrs/pgrs-fepam-rs/`
- `/pgrs/pgrs-iat-parana/`

---

### BLOCO 3 — Erros e Riscos Regulatorios

#### B3.1 CVM 193/2023 NAO OBRIGA PMEs (Regulatorio)
CVM Res. 193/2023 aplica-se a **companhias abertas**, nao a PMEs. O plano confunde obrigacao legal com pressao de supply chain. Conteudo deve distinguir claramente.

**Acao**: Reescrever framing: "CVM 193 obriga empresas de capital aberto, mas o efeito cascata ja afeta fornecedores PMEs que precisam reportar dados ESG para manter contratos."

#### B3.2 RDC ANVISA 222/2018 AUSENTE (Regulatorio)
Regulacao primaria da ANVISA para PGRSS nao e citada. Impossivel publicar conteudo de PGRSS sem ela.

**Acao**: Adicionar RDC 222/2018 como referencia obrigatoria em TODOS os briefs de PGRSS. Criar satelite dedicado.

#### B3.3 CONAMA 307 DESATUALIZADO (Regulatorio)
O plano cita "CONAMA 307/2002" sem mencionar alteracoes por CONAMA 348/2004, 431/2011, 448/2012 e 469/2015.

**Acao**: Referenciar "CONAMA 307/2002 com alteracoes consolidadas" em todo conteudo PGRCC.

#### B3.4 SCOPE DO PGRS EXAGERADO (Regulatorio)
O plano implica que TODA PME precisa de PGRS. Falso. Lei 12.305/2010, Art. 20 obriga apenas: industrias, saude, construcao, grandes geradores (limiares municipais variam), geradores de residuos perigosos, atividades com licenciamento ambiental.

**Acao**: Especificar QUEM e obrigado vs. quem se beneficia voluntariamente. Adicionar tabela de limiares municipais (SP: >200L/dia, RJ: >120L/dia, BH: >100L/dia).

#### B3.5 GEE PARA PMEs E VOLUNTARIO (Regulatorio)
SBCE (Lei 15.042/2024) exige reporte apenas acima de 10.000 tCO2e/ano — exclui a maioria das PMEs. O driver real e supply chain (Escopo 3), nao obrigacao legal.

**Acao**: Separar conteudo em "obrigado por lei" vs. "deveria ter" (supply chain, credito ESG, exportacao).

#### B3.6 DECRETO REGULAMENTADOR SBCE PENDENTE (Regulatorio)
A lei existe mas o decreto regulamentador com detalhes de fases/prazos ainda nao foi publicado. Conteudo que inventa timeline de fases e impreciso.

**Acao**: Disclaimer em todo conteudo SBCE: "lei aprovada, regulamentacao em andamento." Nao fabricar datas de fases.

---

### BLOCO 4 — SEO Tecnico

#### B4.1 CANIBALIZACAO: "Quanto Custa" vs. `/precos/` (SEO)
3 artigos "quanto custa" + `/precos/` competem pelo mesmo intent transacional de pricing.

**Acao**: Opcao recomendada: `/precos/` = pagina de conversao com precos reais. Artigos "quanto custa" = educacional sobre fatores de custo, comparacoes de mercado, SEM tabela de precos propria. Linkam para `/precos/`.

#### B4.2 TITLE TAG BASEADO EM CARACTERES, NAO PIXELS (SEO)
60 chars em portugues frequentemente trunca. Google mede em pixels (~580px), nao caracteres.

**Acao**: Usar medicao por pixel (max 560px). Remover sufixo de marca de satelites (Google appenda automaticamente). Front-load keyword nos primeiros 40 chars.

#### B4.3 SCHEMA MARKUP INCOMPLETO (SEO)
Faltam: Service (precos), HowTo (artigos de processo), ProfessionalService (sobre). FAQ schema em excesso nos pilares (8+ FAQs) pode trigger over-optimization pos-Aug 2023.

**Acao**: Adicionar Service + HowTo. Limitar FAQ schema a satelites (5 perguntas). Remover FAQ schema dos pilares.

#### B4.4 ROBOTS.TXT INCOMPLETO (SEO)
Nao bloqueia: UTM params, `/_next/`, preview URLs, draft mode.

**Acao**: Adicionar: `Disallow: /*?utm_*`, `Disallow: /_next/`, `Disallow: /*?draft=*`, `Disallow: /*?preview=*`

#### B4.5 INP DESATUALIZADO (SEO)
FID foi descontinuado em Mar 2024. O plano ainda referencia "FID/INP < 200ms".

**Acao**: Remover FID. Target INP < 150ms. Especificar estrategias: debounce animacoes, `content-visibility: auto`, lazy-load modais.

---

### BLOCO 5 — Arquitetura Tecnica

#### B5.1 DECISOES P0 PENDENTES (Dev)

| Decisao | Recomendacao | Justificativa |
|---|---|---|
| Next.js version | 15 stable, App Router only | generateMetadata(), Server Components, route groups |
| Content management | MDX no repo (sem CMS) | 4/mes, template rigido, R$0, Git versioning |
| SEO API | Metadata API built-in (DROP next-seo) | next-seo e Pages Router pattern; redundante no App Router |
| Hosting | **Vercel** (obrigatorio para ISR nativo + @vercel/og) | Firebase Hosting NAO suporta ISR |
| JSON-LD | Server Component `<JsonLd>` sem biblioteca | Zero bundle, tipado, auto-gerado do frontmatter |

#### B5.2 RENDERING STRATEGY (Dev)

| Pagina | Estrategia | Revalidacao |
|---|---|---|
| Artigos (pilar + satelite) | SSG | Rebuild on deploy |
| `/precos/` | ISR | 1 hora |
| `/setoriais/` listing | ISR | 24 horas |
| Home | ISR | 1 hora |
| `/blog/` listing | ISR | 1 hora |
| **Nenhuma pagina precisa de SSR** | — | — |

#### B5.3 OG IMAGES AUTOMATICOS (Dev)
80+ artigos nao podem ter OG manual no Canva. Usar `@vercel/og` com `opengraph-image.tsx` por rota.

#### B5.4 SITEMAP PROGRAMATICO (Dev)
Usar `app/sitemap.ts` built-in. Single file ate 1.000 paginas. `lastmod` do frontmatter MDX.

---

### BLOCO 6 — Growth e Go-to-Market

#### B6.1 PRICING TIERED (Growth + CRO)

| Tier | PGRS | GEE | RS | Bundle |
|---|---|---|---|---|
| Standard (10 dias) | R$990 | R$1.290 | R$1.490 | R$2.990 |
| Express (5 dias) | R$1.490 | R$1.790 | R$1.990 | R$4.290 |
| Urgente (48h) | R$2.490 | R$2.990 | R$2.990 | R$6.990 |
| Renovacao anual | R$490 | R$690 | R$790 | R$1.490 |

#### B6.2 PARCERIAS MES 1, NAO MES 8 (Growth)

| Parceiro | Prioridade | Modelo | Quando |
|---|---|---|---|
| Contadores | #1 | 15-20% comissao | Semana 1 |
| Engenheiros ambientais freelance | #2 | 30% (fazem trabalho tecnico) | Semana 1 |
| Advocacia ambiental | #3 | 15% referral | Mes 2 |
| Consultorias ISO 14001 | #4 | White-label 40% desconto | Mes 4 |
| Associacoes (FIEMG, FIESP) | #5 | Pricing institucional | Mes 3 |

#### B6.3 PLG — 3 FERRAMENTAS GRATUITAS (Growth + CRO)

1. **Auto-diagnostico de Compliance** (Mes 1): Quiz 15 perguntas → checklist personalizado → captura email + CNAE. Conversao estimada: 5-15%.
2. **Calculadora de Emissoes GEE** (Mes 2): Ja planejada, mas como PRODUTO nao link bait. Salva resultados, exige email para PDF.
3. **Gerador de PGRS Basico** (Mes 4): Questionario guiado → outline simplificado → "complete profissionalmente por R$990".

#### B6.4 PROJECAO DE RECEITA COMPARATIVA

| Mes | Content-Only (atual) | Multi-Channel (recomendado) |
|---|---|---|
| 1 | R$0 | R$2.470 |
| 3 | R$890 | R$7.120 |
| 6 | R$4.450 | R$17.800 |
| 9 | R$10.680 | R$30.260 |
| 12 | R$28.480 | R$55.180 |

---

### BLOCO 7 — Conteudo Faltante

#### Novos tipos de conteudo recomendados

| Tipo | Quando | Impacto |
|---|---|---|
| Case studies (`/casos/`) | Mes 3+ (1/trimestre) | P0 — social proof critico para B2B compliance |
| Glossario (`/glossario/`) | Mes 2 | P1 — 50-80 termos, low-effort, high-SEO-value |
| Pagina regulatoria (`/regulacoes/`) | Mes 2 | P1 — timeline visual, link magnet, atualizado trimestral |
| Calculadora ROI ("quanto custa NAO ter") | Mes 2 | P1 — muda framing de custo para investimento |
| Comparativos vs. concorrentes | Mes 3-4 (mover de Mes 7) | P1 — highest-converting B2B content |
| Conteudo CBAM para exportadores | Mes 2-3 (mover de Mes 8) | P1 — urgencia real, alta intencao |
| Video YouTube (5-10 min) para pilares | Mes 2+ | P2 — 20% SERPs mostram video |
| LinkedIn carousels | Mes 1+ | P1 — 3-5x mais engagement que text+link |

#### Satelites faltantes nos clusters

| Cluster | Satelite Faltante | Prioridade |
|---|---|---|
| RS | "Matriz de Materialidade ESG: Como Fazer para PMEs" | P1 |
| RS | "Relatorio de Sustentabilidade para Startups: O que Investidores Exigem" | P1 |
| GEE | "Certificacao Carbono Neutro: Como Obter o Selo" | P1 |
| GEE | "GHG Protocol vs ISO 14064: Qual Usar" | P2 |
| PGRS | "Logistica Reversa e PGRS: Decreto 10.936/2022" | P1 |
| PGRS | "Classificacao de Residuos NBR 10004" | P1 |
| PGRS | "PGRS e ISO 14001: Integracao" | P2 |
| Cross | "Economia Circular para PMEs" | P2 |
| Cross | "Selos Verdes para Empresas Brasileiras" | P2 |

#### Regulacoes faltantes que devem ser referenciadas

| Regulacao | Onde usar | Prioridade |
|---|---|---|
| RDC ANVISA 222/2018 | Todo conteudo PGRSS | Critico |
| ABNT NBR 10004:2004 | PGRS industrial | Alto |
| CONAMA 358/2005 | PGRSS (tratamento/disposicao) | Alto |
| ISO 14064-1:2018 | GEE cluster | Medio |
| BACEN Res. 4.945/2021 (PRSAC) | Conteudo "credito bancario" | Alto |
| Decreto 10.936/2022 | PGRS (logistica reversa) | Alto |
| TCFD Recommendations | RS e credito | Medio |

---

## CALENDARIO MES 1 REVISADO

| Semana | Artigo | Mudanca |
|---|---|---|
| 1 | **URGENCIA: Lei 15.042/2024 (SBCE)** | Mover de S2 para S1 (trending first) |
| 2 | **PILAR: PGRS 2025 Guia Completo** | Mover de S1 para S2 (evergreen, pode esperar) |
| 3 | **PILAR: Relatorio Sustentabilidade PME** | Sem mudanca |
| 4 | **PILAR: Inventario de Carbono GEE** | NOVO — substituir "Quanto Custa PGRS" (que vai para Mes 2) |

**Justificativa**: Todos os 3 pilares DEVEM existir antes de qualquer satelite. Artigo de urgencia vai primeiro por first-mover advantage em trending regulatory content.

---

## PROJETO ESTRUTURA RECOMENDADA (Next.js)

```
paloma/
├── app/
│   ├── layout.tsx                    # Root: fonts, analytics, nav
│   ├── page.tsx                      # Home (ISR 1h)
│   ├── sitemap.ts                    # Programmatic
│   ├── robots.ts                     # Programmatic
│   ├── pgrs/
│   │   ├── page.tsx                  # Pilar (SSG)
│   │   └── [slug]/
│   │       ├── page.tsx              # Satelite (SSG)
│   │       └── opengraph-image.tsx   # OG dinamico
│   ├── inventario-carbono/           # Mesma estrutura
│   ├── relatorio-sustentabilidade/   # Mesma estrutura
│   ├── setoriais/
│   ├── blog/
│   ├── precos/
│   ├── glossario/
│   ├── regulacoes/
│   ├── casos/
│   └── sobre/
├── content/                          # MDX (Git-managed)
│   ├── pgrs/
│   ├── inventario-carbono/
│   ├── relatorio-sustentabilidade/
│   ├── setoriais/
│   └── blog/
├── components/
│   ├── mdx/                          # CTA, FAQ, InfoBox, PriceTable, TOC, ArticleMeta
│   ├── layout/                       # Header, Footer, Breadcrumbs
│   └── ui/
├── lib/
│   ├── content.ts                    # MDX reader + frontmatter
│   ├── schema.ts                     # JSON-LD generators
│   ├── metadata.ts                   # generateMetadata helpers
│   └── search-index.ts
├── public/
│   ├── images/
│   └── downloads/                    # PDFs setoriais
├── scripts/
│   ├── validate-content.ts           # CI: quality checks
│   └── generate-search-index.ts
└── .github/workflows/
    ├── deploy.yml
    ├── lighthouse-ci.yml
    └── content-quality.yml
```

---

## PLANO DE ACAO — SEMANA 1

| # | Acao | Owner | Blocker? |
|---|---|---|---|
| 1 | Resolver licenciamento profissional (RT) | Founder | **SIM — bloqueia tudo** |
| 2 | Definir modelo de receita (self-service vs. done-for-you vs. hibrido) | Founder | SIM |
| 3 | Configurar repo paloma com Next.js 15 + App Router + Vercel | Dev | Nao |
| 4 | Implementar pricing tiered (Standard/Express/Urgente) | Founder | Nao |
| 5 | Iniciar outbound para 10 contadores | Founder | Nao |
| 6 | Listar servicos em GetNinjas/Workana | Founder | Nao |
| 7 | Escrever artigo urgencia SBCE (S1) | Content | Depende de #1 (E-E-A-T) |
| 8 | Configurar WhatsApp Business + floating button | Dev | Nao |
| 9 | Criar lead magnet PGRS (checklist PDF) | Content | Nao |
| 10 | Configurar Brevo (email) + formulario de intake | Dev | Nao |

---

*Revisao conduzida por 6 agentes especialistas. Documento original: PLANO_CONTEUDO_SEO v1.0 Final.*
