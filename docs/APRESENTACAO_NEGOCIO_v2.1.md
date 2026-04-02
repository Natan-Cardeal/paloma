# PALOMA — Plataforma de Sustentabilidade para PMEs

**Apresentação de Negócio v2.1** | Abril 2026 | Confidencial

> Este documento consolida a visão estratégica, arquitetura de conteúdo, plano editorial de 12 meses, infraestrutura técnica e projeções de receita da Paloma — plataforma B2B de compliance ambiental para PMEs brasileiras. Versão 2.1 incorpora feedback da especialista técnica (remoção do Inventário GEE como produto) e 50+ recomendações do painel de 6 especialistas.

---

## Índice

1. [Visão Estratégica](#1-visão-estratégica)
2. [Produtos e Posicionamento](#2-produtos-e-posicionamento)
3. [Modelo de Receita e Precificação](#3-modelo-de-receita-e-precificação)
4. [Go-to-Market Multi-Canal](#4-go-to-market-multi-canal)
5. [Arquitetura do Site](#5-arquitetura-do-site)
6. [Topic Clusters e Conteúdo](#6-topic-clusters-e-conteúdo)
7. [Template Universal de Artigo](#7-template-universal-de-artigo)
8. [Briefs Detalhados — Meses 1 a 3](#8-briefs-detalhados--meses-1-a-3)
9. [Calendário Editorial 12 Meses](#9-calendário-editorial-12-meses)
10. [Sistema de Linkagem Interna](#10-sistema-de-linkagem-interna)
11. [SEO Técnico e Schema Markup](#11-seo-técnico-e-schema-markup)
12. [Funil de Conversão](#12-funil-de-conversão)
13. [Amplificação de Conteúdo e Backlinks](#13-amplificação-de-conteúdo-e-backlinks)
14. [KPIs e Sistema de Monitoramento](#14-kpis-e-sistema-de-monitoramento)
15. [Stack Técnico](#15-stack-técnico)
16. [SOP de Produção](#16-sop-de-produção)
17. [Projeções de Receita](#17-projeções-de-receita)
18. [Gestão de Riscos](#18-gestão-de-riscos)
19. [Síntese Estratégica e Próximos Passos](#19-síntese-estratégica-e-próximos-passos)

---

## 1. Visão Estratégica

### 1.1 Posicionamento

Plataforma B2B de compliance ambiental para PMEs brasileiras. Dois produtos core — **PGRS** (Plano de Gerenciamento de Resíduos Sólidos) e **Relatório de Sustentabilidade** — entregues via modelo híbrido (self-service online + done-for-you para casos complexos), com revisão obrigatória por Responsável Técnico (RT) habilitado.

**Diferencial competitivo**: Única plataforma que combina geração automatizada de documentos (PGRS + RS) com revisão por Responsável Técnico habilitado (ART assinada), a preços acessíveis para PMEs. Nenhum concorrente oferece esse modelo híbrido a esse ponto de preço.

### 1.2 Os 4 Pilares Estratégicos

| # | Pilar | Descrição | Métrica-chave |
|---|---|---|---|
| 1 | 🎯 **Topical Authority** | Domínio como referência mais completa do Brasil sobre sustentabilidade para PMEs. Cobertura exaustiva de regulações federais e estaduais. | Posição média GSC, impressões orgânicas |
| 2 | 📈 **Conversão Inteligente** | Cada peça de conteúdo tem papel definido no funil. CTAs calibrados por estágio. Lead magnets, PLG tools e nurture sequences integrados ao fluxo editorial. | Taxa conversão conteúdo→lead, leads qualificados/mês |
| 3 | 📝 **Autonomia Editorial** | Processos documentados, templates rígidos, SOP de produção. Escalável com equipe mínima (1 pessoa produz 4-5 peças/mês). | Tempo médio por peça, consistência de qualidade |
| 4 | 📣 **Go-to-Market Multi-Canal** | Conteúdo é Channel #2. Outbound para contadores é Channel #1. PLG tools, Google Ads e parcerias aceleram receita nos primeiros 90 dias. | Receita por canal, CAC por canal |

### 1.3 Voz Editorial

A comunicação da Paloma segue uma voz editorial consistente:

- **Tom**: Técnico-acessível. Nunca condescendente, nunca hermético. Fala como um consultor experiente que respeita a inteligência do leitor mas simplifica o complexo.
- **Postura**: Autoridade fundamentada em legislação real. Toda afirmação cita lei, resolução ou norma.
- **Persona**: O fundador(a) como autor principal — nome, foto, bio, LinkedIn. RT como revisor técnico com badge de credenciais.
- **Diferenciação**: Honestidade radical — quando consultoria presencial é melhor que a plataforma, dizemos isso. Confiança se constrói com transparência.

### 1.4 E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness)

**BLOQUEADOR RESOLVIDO**: Todo conteúdo técnico (PGRS, RS) exige Responsável Técnico (RT) habilitado com ART. Sem RT, a plataforma configura exercício ilegal da profissão.

| Elemento | Responsável | Onde aparece |
|---|---|---|
| **Autor principal** | Fundador(a) — nome, foto, bio, LinkedIn | Byline de todos os artigos |
| **Revisor técnico** | RT contratado (CRQ/CREA/CRBio conforme tipo) | Badge "Revisado por [Nome], [Registro]" no topo e rodapé |
| **Credenciais exibidas** | ART do profissional, registro no conselho, formação | Página `/sobre/` + schema ProfessionalService |
| **Histórico de atualizações** | Automático via frontmatter MDX | Rodapé dos pilares: "Publicado em X, atualizado em Y" |

**Opções de contratação do RT** (decisão do fundador):

1. **Retainer mensal**: ~R$2.000-3.000/mês (melhor para volume >10 docs/mês)
2. **Fee por documento**: R$200-500/ART (viável no início com <10 documentos/mês) ← **RECOMENDADO para início**
3. **Parceria com engenheiro ambiental freelance**: 30% do valor do serviço

---

## 2. Produtos e Posicionamento

### Dois Produtos Core

| Produto | O que é | Público | Obrigatoriedade | Regulação base |
|---|---|---|---|---|
| **PGRS** | Plano de Gerenciamento de Resíduos Sólidos | PMEs industriais, clínicas, construtoras, comércios | Obrigatório por Lei 12.305/2010 | Lei 12.305/2010 (PNRS), Art. 20-24 |
| **Relatório de Sustentabilidade** | Relatório ESG com indicadores GRI/IFRS | PMEs fornecedoras de grandes empresas, exportadoras, licitações | Pressão de mercado (supply chain, crédito, licitações) | CVM 193/2023 (efeito cascata), GRI 2021 |

### 🔴 Decisão v2.1 — Inventário de Carbono GEE

> **O Inventário de Carbono GEE NÃO será vendido como produto neste momento.**
>
> Esta é a mudança mais significativa da v2.1, baseada no feedback direto da especialista técnica.
>
> **Motivos da decisão:**
> - O inventário GEE é muito caro e complexo — exige consultoria presencial com fornecedores, transportadoras e todos os departamentos da empresa
> - A especialista precisa de experiência comprovada no mercado para assinar um inventário GEE (diferente do RS)
> - PMEs não têm interesse nem mão de obra para mobilizar a empresa inteira para um inventário
> - Quem realiza inventários GEE são empresas grandes (pressão de acionistas, passivos monetários)
> - A equipe precisa aprender mais com o Gabriel (Techpar/Instituto de Tecnologia do Paraná) antes de oferecer
> - Estimativa: ~12 meses até estar pronta para oferecer
>
> **O que fazemos com GEE na v2.1:**
> - ✅ Se a empresa já tiver dados de emissões (escopo 1 e 2), **incorporamos ao Relatório de Sustentabilidade sem custo adicional**
> - ✅ Mantemos todo o conteúdo educacional sobre GEE no site para **autoridade SEO e captura de tráfego**
> - ✅ CTAs do cluster GEE **redirecionam para RS** (não para preços GEE)
> - ✅ Calculadora de emissões GEE mantida como **PLG tool educacional**
> - ❌ Sem página de preços para GEE
> - ❌ Sem oferta de inventário GEE como serviço
> - 🔜 Produto futuro: pode ser adicionado após aprimoramento da equipe (~12 meses)

---

## 3. Modelo de Receita e Precificação

### 3.1 Modelo Híbrido

Duas lanes explícitas em toda a comunicação e na página de preços:

**Lane A — Self-Service Online**
- Cliente preenche questionário guiado na plataforma
- Documento gerado automaticamente + revisado por RT
- Checkout online, preço fixo por tier
- CTA: "Contratar agora", "Gerar meu PGRS"
- Ideal para: PGRS simples, renovações, PMEs com <50 funcionários

**Lane B — Done-for-You (Consultoria)**
- Levantamento presencial/remoto por especialista
- Documento elaborado sob medida + ART
- Proposta personalizada via WhatsApp/email
- CTA: "Fale com especialista", "Solicitar proposta"
- Ideal para: PGRSS, PGRCC complexos, RS com GRI, casos que exigem levantamento presencial

### 3.2 Tabela de Preços (Lane A)

| Tier | PGRS | Relatório de Sustentabilidade | Bundle (PGRS+RS) |
|---|---|---|---|
| **Standard** (10 dias úteis) | R$990 | R$1.490 | R$1.990 (-20%) |
| **Express** (5 dias úteis) | R$1.490 | R$1.990 | R$2.790 (-20%) |
| **Urgente** (48h) | R$2.490 | R$2.990 | R$4.390 (-20%) |
| **Renovação Anual** | R$490 | R$790 | R$990 (-23%) |

> **Nota v2.1**: Inventário GEE **não é oferecido como produto**. Se a empresa já possuir dados de GEE (escopo 1 e 2), eles são incorporados ao Relatório de Sustentabilidade sem custo adicional.

### 3.3 Estratégia de Ancoragem e Upsell

- Exibir sempre os 3 tiers lado a lado (ancoragem: Urgente faz Standard parecer barato)
- Destaque visual no tier Express ("Mais Popular")
- Bundle destacado como "Economize até 20%"
- Renovação anual mencionada em todo artigo de "renovação PGRS" e no email pós-venda

### 3.4 Descontos Estratégicos

| Tipo | Desconto | Condição |
|---|---|---|
| Parceiro contador | 5% para o cliente indicado | Indicação via link rastreável |
| Associação/institucional | 10-15% | FIEMG, FIESP, ACIMINAS, etc. |
| Segundo serviço | 15% no segundo | Comprar PGRS + RS separado (fora do bundle) |
| Pagamento à vista (PIX) | 5% | Checkout único |

### 3.5 Receita Recorrente

- Renovação anual obrigatória para PGRS (Lei 12.305, empresas com licenciamento)
- Update anual de RS (novo período reportado)
- **Meta Mês 12**: 30% da receita vinda de renovações

---

## 4. Go-to-Market Multi-Canal

### 4.1 Estratégia de Canais (desde o Dia 1)

Nenhum canal sozinho sustenta o negócio nos primeiros 6 meses. A combinação de outbound (receita rápida) + ads (volume previsível) + SEO (crescimento composto) + PLG (qualificação automática) cria resiliência.

| # | Canal | CAC Est. | Time to Sale | Prioridade | Budget Mensal | Receita estimada M3 |
|---|---|---|---|---|---|---|
| 1 | **Outbound contadores** | R$0 | 2-4 semanas | P0 (Sem. 1) | Tempo (10h/sem) | R$3.000-5.000 |
| 2 | **Google Ads (high-intent)** | R$50-150/lead | 1-2 semanas | P1 (Mês 1) | R$500-1.000 | R$1.500-3.000 |
| 3 | **Conteúdo SEO** | R$0 | 3-6 meses | P0 (Sem. 1) | Tempo (20h/sem) | R$890-1.500 |
| 4 | **PLG tools** | R$0 | 1-3 meses | P1 (Mês 1) | Dev time (40h total) | R$500-1.000 (leads) |
| 5 | **Marketplaces** (GetNinjas, Workana) | 15-20% comissão | 1 semana | P2 (Mês 1) | Comissão | R$500-1.000 |
| 6 | **Parcerias** (advocacia, ISO) | R$100-200/referral | Mês 2+ | P2 (Mês 2-3) | Comissão | R$500-1.500 |
| 7 | **LinkedIn orgânico** | R$0 | 2-4 semanas | P1 (Mês 1) | Tempo | Brand awareness |

### 4.2 Ecossistema de Parcerias (com timeline)

#### Tier 1 — Semana 1-2 (prioridade máxima)

**Contadores e Escritórios Contábeis**
- Modelo: 15-20% de comissão sobre serviço fechado via indicação
- Abordagem: lista de 50 escritórios no LinkedIn/Google Maps (BH, SP, RJ). Email frio + ligação. Script: "Seus clientes PME provavelmente precisam de PGRS e não sabem. Nós resolvemos, você ganha comissão."
- Entregável: material de 1 página explicando os 2 serviços + tabela de comissões
- Meta Mês 1: 10 contadores contactados, 3 parceiros ativos
- Meta Mês 6: 15 parceiros ativos gerando 10+ leads/mês

**Engenheiros Ambientais Freelance**
- Modelo: 30% do valor do serviço (eles fazem o trabalho técnico, plataforma gerencia cliente e entrega)
- Abordagem: LinkedIn groups de engenharia ambiental, CRQ/CREA regionais, WhatsApp groups
- Vantagem: resolve o problema do RT — eles trazem a ART, plataforma traz o cliente
- Meta Mês 1: 3 engenheiros parceiros (1 por estado: SP, MG, RJ)

#### Tier 2 — Mês 2-3

| Parceiro | Modelo | Abordagem |
|---|---|---|
| Advocacia ambiental | 15% referral fee | 10 escritórios, email personalizado com case |
| Associações (FIEMG, FIESP, FIRJAN) | Pricing institucional com 10-15% desconto | Workshop gratuito como porta de entrada |

#### Tier 3 — Mês 4-6

| Parceiro | Modelo | Abordagem |
|---|---|---|
| Consultorias ISO 14001 | White-label com 40% desconto | Serviço complementar (ISO exige PGRS) |
| Consultorias de RH/ESG | 15% referral fee | Networking em eventos |

### 4.3 PLG Tools Roadmap

| Ferramenta | Mês | URL | Captura | Conversão esperada |
|---|---|---|---|---|
| 🔍 Auto-diagnóstico de Compliance | M1 | `/ferramentas/autodiagnostico/` | Email + CNAE para resultado completo | 5-15% |
| 🧮 Calculadora de Emissões GEE (educacional) | M2 | `/ferramentas/calculadora-emissoes/` | Email para PDF detalhado | 8-20% |
| 📄 Gerador de PGRS Básico | M4 | `/ferramentas/gerador-pgrs/` | Email + dados para DOCX | 10-25% |

> **Nota v2.1**: A calculadora de emissões GEE é mantida como ferramenta educacional. Não vende inventário GEE — redireciona para RS: "Já tem esses dados? Inclua no seu Relatório de Sustentabilidade profissional, a partir de R$1.490."

---

## 5. Arquitetura do Site

### 5.1 Mapa de URLs Completo

```
/                                          # Home (SSG, rebuild on deploy)
│
├── /pgrs/                                 # PILAR — Guia Completo PGRS
│   ├── /pgrs/[slug]/                      # Satélites PGRS (14+)
│   ├── /pgrs/precos/                      # Preços específicos PGRS
│   ├── /pgrs/pgrs-cetesb-sao-paulo/       # Estadual SP
│   ├── /pgrs/pgrs-feam-minas-gerais/      # Estadual MG
│   ├── /pgrs/pgrs-inea-rio-de-janeiro/    # Estadual RJ
│   ├── /pgrs/pgrs-fepam-rs/              # Estadual RS
│   └── /pgrs/pgrs-iat-parana/            # Estadual PR
│
├── /inventario-carbono/                   # PILAR — Guia GEE (INFORMACIONAL — não é produto)
│   └── /inventario-carbono/[slug]/        # Satélites GEE (informacional, sem página de preços)
│
├── /relatorio-sustentabilidade/           # PILAR — Guia Completo RS
│   ├── /relatorio-sustentabilidade/[slug]/ # Satélites RS (14+)
│   └── /relatorio-sustentabilidade/precos/ # Preços específicos RS
│
├── /precos/                               # Página unificada de preços (PGRS + RS + Bundle)
│
├── /glossario/                            # 60+ termos de sustentabilidade
│   └── /glossario/[termo]/               # Página individual por termo
│
├── /regulacoes/                           # Timeline visual regulatória
│   └── /regulacoes/[slug]/               # Página dedicada por regulação
│
├── /casos/                                # Case studies / depoimentos
│   └── /casos/[slug]/                     # Case individual
│
├── /ferramentas/                          # PLG tools (lead capture)
│   ├── /ferramentas/autodiagnostico/      # Quiz compliance (M1)
│   ├── /ferramentas/calculadora-emissoes/ # Calculadora GEE educacional (M2)
│   └── /ferramentas/gerador-pgrs/         # Gerador PGRS básico (M4)
│
├── /setoriais/                            # Relatórios setoriais públicos (PDF + página)
│   └── /setoriais/[slug]/                 # Relatório individual
│
├── /blog/                                 # TOFU + cross-cluster + awareness
│   └── /blog/[slug]/                      # Post individual
│
├── /sobre/                                # Institucional + E-E-A-T + equipe
├── /contato/                              # Formulário de intake + WhatsApp
│
├── /sitemap.xml                           # Programático (app/sitemap.ts)
├── /robots.txt                            # Programático (app/robots.ts)
└── /rss.xml                               # Feed RSS para newsletters
```

### 5.2 Estratégia de Preços nas URLs

| URL | Função | Conteúdo |
|---|---|---|
| `/precos/` | Hub unificado de conversão | Tabela comparativa dos 2 produtos (PGRS + RS), tiers, FAQ de preços, CTA checkout/WhatsApp |
| `/pgrs/precos/` | Landing específica PGRS | Detalhamento do que inclui cada tier PGRS, comparativo mercado, CTA direto |
| `/relatorio-sustentabilidade/precos/` | Landing específica RS | Idem para RS |
| ~~`/inventario-carbono/precos/`~~ | **REMOVIDO v2.1** | GEE não é produto — sem página de preços |
| `/pgrs/quanto-custa-pgrs/` | Artigo educacional | Fatores de custo, faixas de mercado — SEM tabela de preços própria, linka para `/pgrs/precos/` |

**Regra**: Artigos "quanto custa" são educacionais sobre fatores/mercado. Páginas `/precos/` são de conversão com preços reais. Nunca duplicar tabela de preços em artigos.

### 5.3 Rendering Strategy (Firebase Hosting)

> **IMPORTANTE**: Firebase Hosting NÃO suporta ISR nativo. Estratégia adaptada.

| Página | Estratégia | Mecanismo |
|---|---|---|
| Artigos (pilar + satélite) | **Full SSG** | `generateStaticParams()` — rebuild on deploy |
| `/precos/` | **SSG** | Rebuild on deploy (preços mudam raramente) |
| `/glossario/` | **SSG** | `generateStaticParams()` — rebuild on deploy |
| `/regulacoes/` | **SSG** | Rebuild on deploy |
| Home | **SSG** | Rebuild on deploy |
| `/ferramentas/*` | **SSG shell + client-side** | Lógica interativa no client |
| OG images | **Cloud Function** | `satori` + `sharp` via Firebase Cloud Function |
| Sitemap | **Build-time** | `app/sitemap.ts` gera no build |

Com ~51 páginas no ano 1, full SSG com rebuild on deploy (Firebase Hosting + GitHub Actions) é perfeitamente viável. Build time < 60s.

---

## 6. Topic Clusters e Conteúdo

### 6.1 Cluster PGRS (Produto)

**Pilar**: "PGRS 2025: Guia Completo do Plano de Gerenciamento de Resíduos Sólidos para Empresas"
- **URL**: `/pgrs/`
- **Keyword âncora**: "PGRS empresa como fazer"
- **Volume target**: 4.500-5.000 palavras
- **Schema**: Article + BreadcrumbList + HowTo
- **Atualização**: Semestral (+ histórico de atualizações visível)

#### Satélites do Cluster PGRS (14 artigos)

| # | Título | Keyword principal | Intent | Volume |
|---|---|---|---|---|
| P1 | PGRS vs PGRSS vs PGRCC: Diferenças, Obrigações e Qual Você Precisa | pgrs pgrss pgrcc diferença | Informacional | 2.200 |
| P2 | Multa por Falta de PGRS: Valores, Fiscalização e Como Evitar | multa falta pgrs | Informacional/Transacional | 1.800 |
| P3 | Quanto Custa um PGRS em 2025: Fatores, Faixas e Comparativo | quanto custa pgrs | Transacional/Comercial | 1.800 |
| P4 | PGRSS para Clínicas e Consultórios: Guia Completo com RDC 222 | pgrss clínicas consultórios | Transacional | 2.500 |
| P5 | PGRSS para Veterinárias e Clínicas de Estética | pgrss veterinária estética | Transacional | 2.200 |
| P6 | PGRSS para Farmácias e Drogarias | pgrss farmácia | Transacional | 2.000 |
| P7 | PGRCC para Construtoras: CONAMA 307 Consolidado + Guia Prático | pgrcc construtora conama 307 | Transacional | 2.500 |
| P8 | PGRS Indústria Alimentícia: ANVISA + MAPA | pgrs indústria alimentícia | Transacional | 2.200 |
| P9 | PGRS Metalúrgicas e Indústria Química (Classe I) | pgrs metalúrgica química resíduos perigosos | Transacional | 2.200 |
| P10 | Renovação Anual do PGRS: Quando, Como e Quanto Custa | renovação pgrs anual | Transacional | 1.500 |
| P11 | PGRS e Alvará de Funcionamento: Exigências por Município | pgrs alvará funcionamento | Informacional | 1.800 |
| P12 | Logística Reversa e PGRS: Decreto 10.936/2022 | logística reversa pgrs | Informacional | 2.000 |
| P13 | Classificação de Resíduos NBR 10004: Guia Prático | nbr 10004 classificação resíduos | Informacional | 2.000 |
| P14 | PGRS e ISO 14001: Como Integrar | pgrs iso 14001 integração | Informacional | 1.800 |

#### Satélites Estaduais PGRS (5 artigos)

| # | Título | Estado/Órgão | Regulação chave | Mês |
|---|---|---|---|---|
| PE1 | PGRS CETESB São Paulo | SP / CETESB | Dec. Estadual 54.645/2009 | M3 |
| PE2 | PGRS FEAM Minas Gerais | MG / FEAM | DN COPAM 217/2017 | M5 |
| PE3 | PGRS INEA Rio de Janeiro | RJ / INEA | DZ-1310.R-7 INEA | M6 |
| PE4 | PGRS FEPAM Rio Grande do Sul | RS / FEPAM | Portarias FEPAM | M8 |
| PE5 | PGRS IAT Paraná | PR / IAT (ex-IAP) | Resoluções SEMA/PR | M10 |

### 6.2 Cluster GEE — Inventário de Carbono (INFORMACIONAL / AWARENESS)

> **v2.1**: Este cluster existe para **topical authority e SEO**, não para vender inventários GEE como produto. O conteúdo educa o mercado, gera tráfego e direciona leitores para o Relatório de Sustentabilidade. CTAs de preços GEE foram removidos — CTAs redirecionam para `/relatorio-sustentabilidade/precos/` ou `/precos/`.

**Pilar**: "Inventário de Carbono GEE 2025: Guia Completo para Empresas Brasileiras"
- **URL**: `/inventario-carbono/`
- **Keyword âncora**: "inventário de carbono empresa"
- **Volume target**: 4.000-5.000 palavras
- **Schema**: Article + BreadcrumbList + HowTo
- **Papel no funil**: TOFU/MOFU — awareness e autoridade. NÃO é BOFU/conversão direta.

#### Satélites do Cluster GEE (14 artigos — informacional)

| # | Título | Keyword principal | Intent | Volume |
|---|---|---|---|---|
| G1 | Lei 15.042/2024 SBCE: O que Muda para Empresas Brasileiras | lei 15042 2024 sbce mercado carbono | Informacional/Urgência | 2.200 |
| G2 | GHG Protocol na Prática: Como Aplicar em Empresas Brasileiras | ghg protocol empresa brasileira | Informacional | 2.200 |
| G3 | Escopos 1, 2 e 3 de Emissões: Guia Prático com Exemplos | escopos 1 2 3 emissões ghg | Informacional | 2.500 |
| G4 | Inventário de Carbono para Fornecedores de Grandes Empresas | inventário carbono fornecedor | Transacional→RS | 2.300 |
| G5 | Inventário GEE para Transportadoras e Frotas | inventário carbono transporte frota | Transacional→RS | 2.200 |
| G6 | Inventário de Carbono no Agronegócio e Exportação | inventário carbono agronegócio exportação | Transacional→RS | 2.300 |
| G7 | Inventário GEE para Tribunais e Órgãos Públicos: CNJ 594/2024 | inventário carbono tribunais cnj | Transacional→RS | 2.200 |
| G8 | Inventário de Carbono para Eventos Corporativos | inventário carbono eventos | Transacional→RS | 1.800 |
| G9 | Inventário GEE para Construtoras: LEED e AQUA | inventário carbono construção leed | Transacional→RS | 2.000 |
| G10 | Fatores de Emissão MCTI 2025: Tabela Atualizada e Como Usar | fatores emissão mcti 2025 | Informacional | 2.000 |
| G11 | Quanto Custa um Inventário de Carbono GEE em 2025 | quanto custa inventário carbono | Informacional | 1.800 |
| G12 | Certificação Carbono Neutro: Como Obter o Selo | certificação carbono neutro selo | Informacional | 2.000 |
| G13 | GHG Protocol vs ISO 14064: Qual Metodologia Usar | ghg protocol vs iso 14064 | Informacional | 1.800 |
| G14 | CBAM para Exportadores Brasileiros: O que Fazer em 2025 | cbam exportadores brasileiros | Informacional/Urgência | 2.200 |

### 6.3 Cluster RS — Relatório de Sustentabilidade (Produto)

**Pilar**: "Relatório de Sustentabilidade para PMEs 2025: Guia Completo Passo a Passo"
- **URL**: `/relatorio-sustentabilidade/`
- **Keyword âncora**: "relatório de sustentabilidade empresa pequena"
- **Volume target**: 4.000-4.500 palavras
- **Schema**: Article + BreadcrumbList + HowTo
- **Atualização**: Semestral

#### Satélites do Cluster RS (14 artigos)

| # | Título | Keyword principal | Intent | Volume |
|---|---|---|---|---|
| R1 | GRI Standards 2021 Simplificado para PMEs | gri standards pme simplificado | Informacional | 2.500 |
| R2 | CVM 193/2023: Checklist para Companhias Abertas e Efeito Cascata em PMEs | cvm 193 2023 relatório sustentabilidade | Informacional | 2.200 |
| R3 | IFRS S1 e S2: O que PMEs Precisam Saber Sobre Divulgação Climática | ifrs s1 s2 sustentabilidade | Informacional | 2.200 |
| R4 | Relatório de Sustentabilidade e Crédito Bancário: BACEN 4.945 e PRSAC | relatório sustentabilidade crédito banco | Transacional | 2.000 |
| R5 | Relatório Sustentabilidade para Fornecedores de Grandes Empresas | relatório sustentabilidade fornecedor | Transacional | 2.000 |
| R6 | Relatório de Sustentabilidade e Licitações Públicas | relatório sustentabilidade licitação | Transacional | 1.800 |
| R7 | ESG para Empresas com Menos de 50 Funcionários: O que Faz Sentido | esg empresa pequena 50 funcionários | Informacional | 2.000 |
| R8 | Relatório Sustentabilidade para Agronegócio Exportador | relatório sustentabilidade agronegócio | Transacional | 2.200 |
| R9 | Relatório Sustentabilidade para Construtoras e Incorporadoras | relatório sustentabilidade construção | Transacional | 2.000 |
| R10 | Indicadores ESG para PMEs: Quais Medir e Como Reportar | indicadores esg pme | Informacional | 2.200 |
| R11 | Quanto Custa um Relatório de Sustentabilidade em 2025 | quanto custa relatório sustentabilidade | Transacional | 1.800 |
| R12 | Relatório de Sustentabilidade para Franqueados e Redes | relatório sustentabilidade franquia | Transacional | 1.800 |
| R13 | Matriz de Materialidade ESG: Como Fazer para PMEs | matriz materialidade esg pme | Informacional | 2.200 |
| R14 | Relatório de Sustentabilidade para Startups: O que Investidores Exigem | relatório sustentabilidade startup investidor | Informacional/Transacional | 2.000 |

### 6.4 Conteúdo Cross-Cluster (`/blog/`)

Artigos TOFU e de awareness que não pertencem a um cluster específico, mas linkam para todos:

| # | Título | Keyword | Tipo | Mês |
|---|---|---|---|---|
| B1 | O que é ESG e Por Que Sua Empresa Precisa se Preocupar em 2025 | esg empresa 2025 | TOFU/Awareness | M3 |
| B2 | 5 Multas Ambientais que PMEs Recebem Sem Saber | multa ambiental pme | TOFU/Awareness | M4 |
| B3 | Sustentabilidade Empresarial: Modismo ou Obrigação Legal? | sustentabilidade empresarial obrigação | TOFU/Awareness | M4 |
| B4 | Seu Contador Deveria Ter Te Avisado Sobre Isso (Compliance Ambiental) | compliance ambiental contador | TOFU/Awareness | M5 |
| B5 | Economia Circular para PMEs: Oportunidades e Primeiros Passos | economia circular pme | TOFU/Awareness | M5 |
| B6 | Selos Verdes para Empresas Brasileiras: Quais Existem e Como Obter | selos verdes empresas brasil | TOFU/Awareness | M6 |
| B7 | Plataforma de Compliance Ambiental vs. Consultoria Tradicional: Comparativo | plataforma compliance vs consultoria | MOFU/Comparativo | M3 |
| B8 | Contadores e Compliance Ambiental: Uma Parceria Necessária | contador compliance ambiental parceria | MOFU/Parceria | M8 |
| B9 | Calendário Regulatório Ambiental 2025 (Bônus) | calendário regulatório ambiental 2025 | Informacional | M3 |

### 6.5 Relatórios Setoriais

| # | Setor | Mês | Formato |
|---|---|---|---|
| 1 | Construção Civil | M6 | PDF + página web |
| 2 | Indústria Alimentícia | M7 | PDF + página web |
| 3 | Saúde | M8 | PDF + página web |
| 4 | Agronegócio | M9 | PDF + página web |
| 5 | Anuário Consolidado PMEs (link bait) | M12 | PDF + página web |

### 6.6 Glossário de Sustentabilidade

- **Hub**: `/glossario/` — 60+ termos, índice A-Z, agrupados por tema (Resíduos, Carbono, ESG/RS, Regulações, Certificações)
- **Individuais**: `/glossario/[termo]/` — definição curta + contexto para PMEs + link para artigo relevante + regulação aplicável
- **Termos prioritários (primeiros 30)**: ART, BACEN 4.945, Carbono neutro, CBAM, CETESB, Classe I/II resíduos, CONAMA 307, CONAMA 358, CRQ/CREA, CVM 193, Economia circular, Escopo 1/2/3, ESG, GHG Protocol, GRI, Inventário GEE, ISO 14001, ISO 14064, LEED, Logística reversa, Materialidade ESG, NBR 10004, PGRCC, PGRS, PGRSS, PNRS, RDC 222, Relatório de sustentabilidade, SBCE, TCFD
- **Schema**: DefinedTerm (individuais) + BreadcrumbList
- **Publicação**: M2 (hub + primeiros 30 termos; adições incrementais)

---

## 7. Template Universal de Artigo

### 7.1 Campos de Metadados (Frontmatter MDX)

```yaml
---
title: ""                    # Title tag (max 560px, front-load keyword)
h1: ""                       # H1 visível (pode diferir do title)
metaDescription: ""          # Max 920px (~150-155 chars PT-BR)
keyword: ""                  # Keyword principal
keywordsSecondary: []        # Keywords secundárias (3-5)
intent: ""                   # informacional | transacional | comercial | navegacional
personaPrimaria: ""          # Ex: "Gestor de PME industrial, 35-50 anos, SP"
diferencialCompetitivo: ""   # O que este artigo faz que nenhum concorrente faz
clusterParent: ""            # pgrs | inventario-carbono | relatorio-sustentabilidade | blog
pageType: ""                 # pilar | satelite | tofu | comparativo | urgencia | ferramenta
regulacoes: []               # Regulações obrigatórias a citar
author: ""                   # Nome do autor
technicalReviewer: ""        # Nome do RT + registro profissional
publishedAt: ""              # ISO date
updatedAt: ""                # ISO date
updateHistory: []            # Array de {date, description} para pilares
wordCount: 0                 # Target
schema: []                   # Tipos de schema: Article, FAQPage, HowTo, BreadcrumbList
---
```

### 7.2 Os 14 Blocos do Template

| # | Bloco | Descrição | Regras |
|---|---|---|---|
| 1 | **Title Tag** | Keyword front-loaded nos primeiros 40 chars. Max 560px. Sem sufixo de marca em satélites. | Medir com ferramenta de pixel (SERP Simulator) |
| 2 | **Meta Description** | Max 920px (~150-155 chars). Fórmula: [Problema] + [Solução] + [CTA implícito]. Sem ponto final. | Medir por pixel, não por caractere |
| 3 | **H1** | Próximo do Title Tag, pode ser mais longo/descritivo. Keyword obrigatória. Único por página. | Max 70 chars (flexível) |
| 4 | **Badge E-E-A-T** | "Revisado por [Nome do RT], [CRQ/CREA XXX] — Última atualização: [data]" | Visível no topo, abaixo do H1 |
| 5 | **Introdução** | 150-200 palavras. Fórmula: Problema → Consequência → Promessa → Âncora para pilar. | Keyword nos primeiros 100 chars |
| 6 | **Índice (ToC)** | Links de âncora para cada H2. Gerado automaticamente via `<TOC />`. | Sticky em desktop, colapsável em mobile |
| 7 | **Corpo H2s** | Min 5 H2s (satélites), 8-10 H2s (pilares). Cada H2 = subtema com intenção de busca própria. | Min 1 tabela + 1 lista por artigo |
| 8 | **CTA Intermediário** | Após o 3o H2. Contextual ao conteúdo. Linka para pilar ou ferramenta PLG. | `<CTAMid>` — **NUNCA** para preços |
| 9 | **Dados e Referências** | Citações de leis, resoluções, normas. Links para fontes oficiais. | Min 3 referências por artigo |
| 10 | **Social Proof** | Depoimento, número de documentos, logos, badge CRQ/CREA. | `<SocialProof />` — placeholder até ter cases reais |
| 11 | **FAQ** | **Apenas em satélites**: max 5 perguntas, JSON-LD FAQPage Schema. **Pilares NÃO têm FAQ schema.** | Perguntas reais de clientes/GSC |
| 12 | **CTA Final** | Linka para `/precos/` ou `/[cluster]/precos/` OU WhatsApp. | `<CTAFinal type="pricing" />` ou `<CTAFinal type="whatsapp" />` |
| 13 | **Caixas de Destaque** | Avisos regulatórios, disclaimers, alertas de prazo. | `<InfoBox type="warning|info|deadline" />` |
| 14 | **Rodapé do Artigo** | Data, última atualização, bio do autor + bio do RT. Pilares: "Histórico de Atualizações". | `<ArticleFooter />` com dados do frontmatter |

### 7.3 Parâmetros de Qualidade

| Parâmetro | Pilar | Satélite | Blog TOFU |
|---|---|---|---|
| Palavras mínimas | 3.500 | 1.800 | 1.500 |
| H2s mínimos | 8 | 5 | 4 |
| Links internos mín. | 5 | 3 | 3 |
| Referências externas mín. | 5 | 3 | 2 |
| FAQ schema | NÃO | SIM (max 5) | Opcional |
| Tabelas mín. | 2 | 1 | 0 |
| Badge E-E-A-T | SIM | SIM | SIM |
| Histórico de atualizações | SIM | NÃO | NÃO |

### 7.4 Regras de CTA

| Posição | Tipo de CTA | Destino | Exemplo |
|---|---|---|---|
| Mid-article (após 3o H2) | Contextual, educacional | Pilar do cluster OU ferramenta PLG | "Saiba tudo sobre PGRS no nosso guia completo" |
| Final do artigo | Conversão direta | `/precos/`, `/[cluster]/precos/` ou WhatsApp | "Gere seu PGRS profissional a partir de R$990" |
| Sidebar/sticky (desktop) | Lead magnet | Download PDF/checklist (captura email) | "Baixe o checklist PGRS gratuito" |
| Exit intent (modal) | Newsletter ou lead magnet | Formulário email | "Receba alertas de mudanças regulatórias" |

> **REGRA ABSOLUTA**: CTA mid-article NUNCA linka diretamente para preços. O leitor ainda está consumindo conteúdo — o CTA deve aprofundar conhecimento (pilar) ou gerar engajamento (ferramenta). CTA final é o momento da conversão.

---

## 8. Briefs Detalhados — Meses 1 a 3

### 📅 MÊS 1 — FUNDAÇÃO (5 peças)

**Tema**: Estabelecer os 3 pilares + capturar urgência regulatória + lançar primeiro PLG tool
**Objetivo**: Ter toda a arquitetura de hubs publicada antes de qualquer satélite

---

#### M1-S1: URGÊNCIA — Lei 15.042/2024 SBCE

| Campo | Detalhe |
|---|---|
| **Título** | Lei 15.042/2024: O que o Mercado Regulado de Carbono (SBCE) Muda para Sua Empresa |
| **URL** | `/inventario-carbono/lei-15042-2024-sbce-mercado-carbono/` |
| **Keyword principal** | lei 15042 2024 sbce mercado carbono |
| **Keywords secundárias** | mercado regulado carbono brasil, sbce o que é, sistema brasileiro comércio emissões |
| **Intenção de busca** | Informacional com urgência regulatória |
| **Persona primária** | Diretor de compliance em empresa industrial média (100-500 funcionários) |
| **Diferencial** | Único conteúdo que separa "obrigado por lei" (>10.000 tCO2e/ano) vs. "deveria ter por supply chain" (PMEs fornecedoras), COM disclaimer regulamentação pendente |
| **Volume** | 2.200 palavras |
| **Meta-description** | Lei 15.042/2024 criou o SBCE — mercado regulado de carbono no Brasil. Entenda quem é obrigado, prazos e como PMEs são impactadas pelo efeito cascata |
| **Prazo** | Mês 1, Semana 1 |

**Estrutura H2s**:
- H2: O que é a Lei 15.042/2024 e o SBCE
- H2: Quem está obrigado pelo SBCE (limiar de 10.000 tCO2e/ano)
- H2: Por que PMEs abaixo do limiar também serão impactadas (Escopo 3)
- H2: Status da regulamentação: o que já está definido e o que falta
- H2: Como sua empresa pode se preparar agora (3 passos práticos)

**CTA final**: "Inclua dados de emissões no seu Relatório de Sustentabilidade → Ver preços RS" (linka `/relatorio-sustentabilidade/precos/`)
**CTA mid-article**: "Entenda tudo sobre inventários GEE no nosso guia completo" (linka `/inventario-carbono/`)
**Disclaimer obrigatório**: "A Lei 15.042/2024 foi sancionada, porém o decreto regulamentador com detalhes de fases, prazos e limiares específicos ainda não foi publicado."
**Schema**: Article + BreadcrumbList (sem FAQ — urgência, atualizar frequentemente)

---

#### M1-S2: PILAR PGRS

| Campo | Detalhe |
|---|---|
| **Título** | PGRS 2025: Guia Completo do Plano de Gerenciamento de Resíduos Sólidos para Empresas |
| **URL** | `/pgrs/` |
| **Keyword principal** | pgrs empresa como fazer |
| **Keywords secundárias** | plano gerenciamento resíduos sólidos, pgrs obrigatório, pgrs 2025, como fazer pgrs empresa |
| **Intenção de busca** | Informacional com alta intenção transacional |
| **Persona primária** | Gestor de PME industrial (50-200 funcionários) que precisa de PGRS para licenciamento |
| **Diferencial** | Guia mais completo do Brasil: tabela de obrigatoriedade com limiares municipais, passo a passo com cronograma, todas regulações consolidadas, diferenciação PGRS/PGRSS/PGRCC |
| **Volume** | 4.500-5.000 palavras |
| **Meta-description** | Guia completo do PGRS 2025 para empresas. Saiba quem é obrigado, como elaborar passo a passo, custos e como evitar multas de até R$50 milhões |
| **Prazo** | Mês 1, Semana 2 |

**Estrutura H2s**:
- H2: O que é PGRS e por que sua empresa pode ser obrigada a ter
- H2: Quem precisa de PGRS: obrigatoriedade por lei vs. benefício voluntário (tabela Art. 20 Lei 12.305)
- H2: PGRS vs PGRSS vs PGRCC: qual você precisa (tabela comparativa)
- H2: Limiares municipais: quando sua empresa é "grande geradora" (SP, RJ, BH, POA, CWB)
- H2: Passo a passo para elaborar um PGRS profissional (8 etapas)
- H2: Documentos e credenciais necessárias (ART, RT, CRQ/CREA)
- H2: Multas e penalidades por falta de PGRS (Lei 9.605/1998)
- H2: Quanto custa um PGRS e como escolher fornecedor
- H2: Renovação anual: o que muda e quando atualizar
- H2: Perguntas frequentes sobre PGRS (NÃO usar FAQ schema — pilar)

**CTA final**: "Gere seu PGRS profissional com revisão técnica → Ver preços" (linka `/pgrs/precos/`)
**CTA mid-article**: "Descubra se sua empresa precisa de PGRS com nosso autodiagnóstico gratuito" (linka `/ferramentas/autodiagnostico/`)
**Regulações**: Lei 12.305/2010 Art. 20-24, Decreto 10.936/2022, Lei 9.605/1998, NBR 10004:2004
**Schema**: Article + BreadcrumbList + HowTo

---

#### M1-S3: PILAR Relatório de Sustentabilidade

| Campo | Detalhe |
|---|---|
| **Título** | Relatório de Sustentabilidade para PMEs 2025: Guia Completo Passo a Passo |
| **URL** | `/relatorio-sustentabilidade/` |
| **Keyword principal** | relatório de sustentabilidade empresa pequena |
| **Keywords secundárias** | relatório sustentabilidade pme, como fazer relatório sustentabilidade, relatório esg pme |
| **Intenção de busca** | Informacional com intenção transacional média |
| **Persona primária** | Diretor ou sócio de PME (20-100 funcionários) que recebeu cobrança de cliente grande para apresentar relatório ESG |
| **Diferencial** | Único guia que: distingue obrigação legal (CVM 193) de pressão de mercado, oferece framework simplificado para PMEs, conecta RS com benefícios concretos (crédito, licitações, supply chain) |
| **Volume** | 4.000-4.500 palavras |
| **Meta-description** | Como criar um relatório de sustentabilidade para PMEs em 2025. Framework simplificado, indicadores essenciais e como usar para crédito, licitações e supply chain |
| **Prazo** | Mês 1, Semana 3 |

**Estrutura H2s**:
- H2: O que é um relatório de sustentabilidade e por que PMEs estão sendo cobradas
- H2: CVM 193/2023: quem é obrigado por lei vs. quem é impactado pelo efeito cascata
- H2: Frameworks disponíveis: GRI, SASB, IFRS S1/S2 — qual usar para PMEs
- H2: Framework simplificado: 15 indicadores essenciais para sua primeira versão
- H2: Passo a passo para elaborar seu relatório (6 etapas)
- H2: Matriz de materialidade: como identificar o que importa para seu negócio
- H2: Como usar seu relatório para conseguir crédito bancário (BACEN 4.945)
- H2: Relatório de sustentabilidade em licitações públicas (Lei 14.133/2021)
- H2: Quanto custa e como escolher entre plataforma e consultoria

**CTA final**: "Crie seu relatório de sustentabilidade profissional → Ver preços" (linka `/relatorio-sustentabilidade/precos/`)
**Regulações**: CVM 193/2023, GRI 2021, IFRS S1/S2, BACEN 4.945/2021, Lei 14.133/2021
**Schema**: Article + BreadcrumbList + HowTo

---

#### M1-S4: PILAR Inventário de Carbono GEE (INFORMACIONAL)

> **v2.1**: Este pilar é puramente educacional/SEO. Não vendemos inventário GEE como serviço. Serve para: topical authority, captar tráfego de alta qualidade, direcionar para RS.

| Campo | Detalhe |
|---|---|
| **Título** | Inventário de Carbono GEE 2025: Guia Completo para Empresas Brasileiras |
| **URL** | `/inventario-carbono/` |
| **Keyword principal** | inventário de carbono empresa |
| **Keywords secundárias** | inventário gee empresa, como fazer inventário carbono, inventário emissões gases efeito estufa |
| **Intenção de busca** | Informacional (awareness — sem conversão direta para produto GEE) |
| **Persona primária** | Gestor ambiental em empresa média que precisa reportar emissões para cliente grande |
| **Volume** | 4.000-5.000 palavras |
| **Meta-description** | Guia completo do inventário de carbono GEE para empresas brasileiras em 2025. Escopos 1, 2 e 3, GHG Protocol, SBCE e como reduzir custos com gestão de emissões |
| **Prazo** | Mês 1, Semana 4 |

**Estrutura H2s**:
- H2: O que é um inventário de carbono e por que sua empresa deveria ter um
- H2: Obrigação legal vs. voluntário: SBCE, supply chain e crédito ESG
- H2: GHG Protocol: a metodologia padrão para inventários no Brasil
- H2: Escopos 1, 2 e 3 explicados com exemplos brasileiros
- H2: Fatores de emissão MCTI: como usar a tabela oficial brasileira
- H2: Passo a passo para elaborar seu inventário GEE (7 etapas)
- H2: Verificação e publicação: Programa GHG Protocol Brasil e Registro Público
- H2: Quanto custa e como escolher entre plataforma e consultoria
- H2: SBCE e o futuro do mercado de carbono brasileiro

**CTA final**: "Já tem dados de emissões? Inclua no seu Relatório de Sustentabilidade → Ver preços RS" (linka `/relatorio-sustentabilidade/precos/`)
**CTA mid-article**: "Calcule suas emissões gratuitamente com nossa calculadora" (linka `/ferramentas/calculadora-emissoes/`)
**Schema**: Article + BreadcrumbList + HowTo

---

#### M1-BÔNUS: Auto-diagnóstico de Compliance Ambiental (PLG Tool)

| Campo | Detalhe |
|---|---|
| **URL** | `/ferramentas/autodiagnostico/` |
| **Tipo** | Ferramenta interativa (quiz), NÃO artigo |
| **Mecânica** | 15 perguntas (CNAE, funcionários, faturamento, estado, tipo resíduo, exporta?, fornecedor de grande empresa?) |
| **Output** | Checklist personalizado com documentos obrigatórios vs. recomendados |
| **Gate** | Email + CNAE obrigatórios para resultado completo |
| **Conversão** | 5-15% para lead qualificado |
| **Implementação** | SSG shell + client-side (React state, sem backend) |
| **Prazo** | Mês 1, Semana 4 |

**Total Mês 1**: ~15.400 palavras + 1 ferramenta interativa

---

### 📅 MÊS 2 — SEGMENTAÇÃO + URGÊNCIA (5 peças)

**Tema**: Primeiros satélites de alta transacionalidade + urgência internacional + glossário
**Objetivo**: Começar a rankear para termos transacionais de nicho

---

#### M2-S1: Quanto Custa um PGRS em 2025

| Campo | Detalhe |
|---|---|
| **Título** | Quanto Custa um PGRS em 2025: Fatores, Faixas de Preço e Como Economizar |
| **URL** | `/pgrs/quanto-custa-pgrs/` |
| **Keyword principal** | quanto custa pgrs |
| **Intenção** | Transacional/Comercial |
| **Volume** | 1.800 palavras |
| **Meta-description** | Descubra quanto custa um PGRS em 2025. Faixas de preço por porte, fatores que influenciam o valor e como escolher a melhor opção para sua empresa |
| **Prazo** | Mês 2, Semana 1 |

**Estrutura H2s**: Faixas de preço no mercado → 6 fatores de custo → Plataforma vs. consultoria vs. freelance → Como economizar → O custo de NÃO ter PGRS
**CTA final**: "Veja nossos preços transparentes para PGRS" → `/pgrs/precos/`
**Schema**: Article + BreadcrumbList + FAQPage (5 perguntas sobre preços)

---

#### M2-S2: PGRSS para Clínicas e Consultórios

| Campo | Detalhe |
|---|---|
| **Título** | PGRSS para Clínicas e Consultórios: Guia Completo com RDC 222/2018 |
| **URL** | `/pgrs/pgrss-clinicas-consultorios/` |
| **Keyword principal** | pgrss clínicas consultórios |
| **Intenção** | Transacional |
| **Volume** | 2.500 palavras |
| **Meta-description** | Como elaborar o PGRSS da sua clínica ou consultório. Guia completo com RDC 222/2018 ANVISA, CONAMA 358 e passo a passo para adequação em 2025 |
| **Prazo** | Mês 2, Semana 2 |

**Estrutura H2s**: O que é PGRSS → RDC ANVISA 222/2018 → Classificação Grupos A-E → CONAMA 358/2005 → Passo a passo → Quem pode assinar (RT)
**CTA final**: "Gere seu PGRSS profissional com revisão por RT habilitado → Ver preços" → `/pgrs/precos/`
**Schema**: Article + BreadcrumbList + FAQPage

---

#### M2-S3: CBAM para Exportadores Brasileiros

| Campo | Detalhe |
|---|---|
| **Título** | CBAM para Exportadores Brasileiros: O que Fazer em 2025 |
| **URL** | `/inventario-carbono/cbam-exportadores-brasileiros/` |
| **Keyword principal** | cbam exportadores brasileiros |
| **Intenção** | Informacional com urgência real (fase transitória em andamento) |
| **Volume** | 2.200 palavras |
| **Meta-description** | O CBAM da UE já está em fase transitória e afeta exportadores brasileiros. Saiba quais setores, prazos e como preparar seu inventário de carbono |
| **Prazo** | Mês 2, Semana 3 |

**Estrutura H2s**: O que é CBAM → Setores afetados → Cronograma → O que exportadores precisam reportar → Como um inventário GEE prepara para o CBAM
**CTA final**: "Documente suas emissões no seu Relatório de Sustentabilidade → Ver preços RS" → `/relatorio-sustentabilidade/precos/`
**Schema**: Article + BreadcrumbList + FAQPage

---

#### M2-S4: Glossário de Sustentabilidade (60+ termos)

| Campo | Detalhe |
|---|---|
| **URL hub** | `/glossario/` |
| **URLs individuais** | `/glossario/[termo]/` |
| **Keyword principal** | glossário sustentabilidade empresarial |
| **Volume** | Hub: 5.000-8.000 palavras; individuais: 200-400 cada |
| **Prazo** | Mês 2, Semana 4 (hub + 30 termos; incremento contínuo) |

**Schema**: DefinedTerm (individuais) + BreadcrumbList
**Impacto SEO**: Low-effort, high-value. Cada termo é uma página indexável para "[termo] significado" e gera links internos para todo o site.

---

#### M2-BÔNUS: Calculadora de Emissões GEE (PLG Tool — EDUCACIONAL)

| Campo | Detalhe |
|---|---|
| **URL** | `/ferramentas/calculadora-emissoes/` |
| **Inputs** | Eletricidade (kWh/mês), combustível (L/mês), viagens aéreas, frota, GLP/gás natural |
| **Output** | Estimativa tCO2e/ano por escopo + gráfico visual + comparativo setorial |
| **Gate** | Email obrigatório para PDF detalhado |
| **Upsell** | "Inclua esses dados no seu Relatório de Sustentabilidade profissional, a partir de R$1.490" |
| **Prazo** | Mês 2, Semana 3-4 |

**Total Mês 2**: ~11.500+ palavras + 1 ferramenta interativa

---

### 📅 MÊS 3 — AUTORIDADE + COMPARATIVOS (5 peças + bônus)

**Tema**: Primeiro conteúdo estadual, comparativo competitivo, checklist regulatório
**Objetivo**: Expandir cobertura geográfica, posicionar contra consultorias tradicionais

---

#### M3-S1: PGRCC para Construtoras

| Campo | Detalhe |
|---|---|
| **Título** | PGRCC para Construtoras: Guia Completo CONAMA 307 Consolidado (2002-2015) |
| **URL** | `/pgrs/pgrcc-construtoras-conama-307/` |
| **Keyword** | pgrcc construtora conama 307 |
| **Intenção** | Transacional |
| **Volume** | 2.500 palavras |
| **Diferencial** | ÚNICO conteúdo que consolida TODAS as alterações da CONAMA 307: original 2002 + 348/2004 + 431/2011 + 448/2012 + 469/2015 |
| **Prazo** | Mês 3, Semana 1 |

**CTA final**: "Gere seu PGRCC com revisão técnica → Ver preços" → `/pgrs/precos/`

---

#### M3-S2: Plataforma vs. Consultoria Tradicional

| Campo | Detalhe |
|---|---|
| **Título** | Plataforma de Compliance Ambiental vs. Consultoria Tradicional: Comparativo Completo |
| **URL** | `/blog/plataforma-compliance-vs-consultoria-tradicional/` |
| **Keyword** | plataforma compliance ambiental vs consultoria |
| **Intenção** | Comercial/Comparativo (MOFU) |
| **Volume** | 2.200 palavras |
| **Diferencial** | Comparativo honesto — reconhece quando consultoria é melhor opção |
| **Prazo** | Mês 3, Semana 2 |

**CTA final**: "Conheça nosso modelo híbrido → Ver preços" → `/precos/`

---

#### M3-S3: CVM 193/2023 Checklist

| Campo | Detalhe |
|---|---|
| **Título** | CVM 193/2023: Checklist de Divulgação de Sustentabilidade (e Efeito Cascata em PMEs) |
| **URL** | `/relatorio-sustentabilidade/cvm-193-2023-checklist/` |
| **Keyword** | cvm 193 2023 relatório sustentabilidade |
| **Intenção** | Informacional (regulatório) |
| **Volume** | 2.200 palavras |
| **Disclaimer** | "A CVM 193/2023 aplica-se a companhias abertas registradas na CVM. PMEs não são obrigadas diretamente, mas podem ser impactadas pelas exigências de reporte dos seus clientes de capital aberto." |
| **Prazo** | Mês 3, Semana 3 |

**CTA final**: "Elabore seu relatório de sustentabilidade profissional → Ver preços" → `/relatorio-sustentabilidade/precos/`

---

#### M3-S4: PGRS CETESB São Paulo

| Campo | Detalhe |
|---|---|
| **Título** | PGRS CETESB São Paulo: Requisitos Específicos, Formulários e Passo a Passo |
| **URL** | `/pgrs/pgrs-cetesb-sao-paulo/` |
| **Keyword** | pgrs cetesb são paulo |
| **Intenção** | Transacional (alta — busca local por necessidade imediata) |
| **Volume** | 2.000 palavras |
| **Diferencial** | Único guia 100% focado em CETESB com links diretos para formulários e limiares de SP |
| **Prazo** | Mês 3, Semana 4 |

**CTA final**: "Gere seu PGRS para SP com revisão técnica → Ver preços" → `/pgrs/precos/`
**Justificativa**: SP é o maior mercado. Conteúdo estadual captura busca local de alta intenção.

---

#### M3-BÔNUS: Calendário Regulatório Ambiental 2025

| Campo | Detalhe |
|---|---|
| **URL** | `/regulacoes/calendario-regulatorio-2025/` |
| **Tipo** | Página visual com timeline (NÃO artigo longo) |
| **Formato** | Timeline mês a mês (Jan-Dez), com filtro por tipo (Resíduos/Carbono/ESG/Todos) |
| **CTA** | "Receba alertas por email quando um prazo se aproximar" (captura email) |
| **Impacto** | Link magnet poderoso — outros sites referenciam como recurso útil |
| **Prazo** | Mês 3, Semana 4 |

**Total Mês 3**: ~10.400 palavras + 1 página visual

---

## 9. Calendário Editorial 12 Meses

### Visão Geral

| Período | Peças/mês | Total peças | Foco |
|---|---|---|---|
| M1-M3 (Fundação) | 5/mês | 15 + 3 bônus | Pilares, urgência, primeiros satélites, PLG tools, glossário |
| M4-M6 (Expansão) | 4/mês | 12 | Segmentação por setor, TOFU, estaduais, cases |
| M7-M9 (Escala) | 4/mês | 12 | Cauda longa, setoriais, refresh pilares, estaduais |
| M10-M12 (Consolidação) | 4/mês | 12 | Profundidade técnica, campanhas conversão, planejamento ano 2 |
| **TOTAL** | — | **51 + 3 bônus** | — |

### Calendário Mensal Detalhado

#### Mês 1 — FUNDAÇÃO: Pilares + Urgência

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Lei 15.042/2024 SBCE: O que Muda para Sua Empresa | Urgência regulatória | GEE | 2.200 |
| S2 | PGRS 2025: Guia Completo | **PILAR** | PGRS | 4.500 |
| S3 | Relatório de Sustentabilidade para PMEs 2025 | **PILAR** | RS | 4.200 |
| S4 | Inventário de Carbono GEE 2025: Guia Completo | **PILAR** (informacional) | GEE | 4.500 |
| Bônus | Auto-diagnóstico de Compliance Ambiental | PLG Tool | Cross | — |

**Total**: ~15.400 palavras + 1 ferramenta

#### Mês 2 — SEGMENTAÇÃO: Satélites Transacionais + Urgência Internacional

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Quanto Custa um PGRS em 2025 | Satélite transacional | PGRS | 1.800 |
| S2 | PGRSS para Clínicas e Consultórios (RDC 222) | Satélite transacional | PGRS | 2.500 |
| S3 | CBAM para Exportadores Brasileiros | Satélite urgência | GEE | 2.200 |
| S4 | Glossário de Sustentabilidade (60+ termos) | Asset SEO permanente | Cross | 5.000+ |
| Bônus | Calculadora de Emissões GEE | PLG Tool (educacional) | GEE | — |

**Total**: ~11.500+ palavras + 1 ferramenta

#### Mês 3 — AUTORIDADE: Comparativos + Estadual + Regulatório

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | PGRCC Construtoras CONAMA 307 Consolidado | Satélite transacional | PGRS | 2.500 |
| S2 | Plataforma vs. Consultoria Tradicional | Comparativo MOFU | Blog | 2.200 |
| S3 | CVM 193/2023 Checklist | Satélite regulatório | RS | 2.200 |
| S4 | PGRS CETESB São Paulo | Satélite estadual | PGRS | 2.000 |
| Bônus | Calendário Regulatório Ambiental 2025 | Página visual/referência | Regulações | 1.500 |

**Total**: ~10.400 palavras + 1 página visual

#### Mês 4 — EXPANSÃO: Setores + TOFU

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | PGRS Indústria Alimentícia: ANVISA + MAPA | Satélite transacional | PGRS | 2.200 |
| S2 | 5 Multas Ambientais que PMEs Recebem Sem Saber | TOFU awareness | Blog | 1.800 |
| S3 | Inventário Carbono para Fornecedores de Grandes Empresas | Satélite transacional | GEE | 2.300 |
| S4 | Sustentabilidade Empresarial: Modismo ou Obrigação Legal? | TOFU awareness | Blog | 2.000 |

**Total**: ~8.300 palavras | **Bônus**: Gerador de PGRS Básico (PLG Tool M4)

#### Mês 5 — RETENÇÃO: Recorrência + TOFU + Estadual

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Renovação Anual do PGRS: Quando e Como | Satélite transacional | PGRS | 1.500 |
| S2 | Seu Contador Deveria Ter Te Avisado (Compliance) | TOFU awareness | Blog | 1.800 |
| S3 | PGRS FEAM Minas Gerais | Satélite estadual | PGRS | 2.000 |
| S4 | Crédito BNDES/ESG + Inventário GEE | Satélite transacional | GEE | 2.000 |

**Total**: ~7.300 palavras | **Bônus**: Primeiro case study (se houver cliente real)

#### Mês 6 — CONSOLIDAÇÃO: Autoridade Técnica + TOFU

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Escopos 1, 2 e 3 de Emissões: Guia Prático | Satélite informacional | GEE | 2.500 |
| S2 | PGRS INEA Rio de Janeiro | Satélite estadual | PGRS | 2.000 |
| S3 | Selos Verdes para Empresas Brasileiras | TOFU awareness | Blog | 2.000 |
| S4 | RELATÓRIO SETORIAL: Emissões na Construção Civil 2025 | Setorial público | Setoriais | 3.000 |

**Total**: ~9.500 palavras

#### Mês 7 — ESCALA: Cauda Longa + Setorial

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | PGRS Metalúrgicas e Indústria Química (Classe I) | Satélite transacional | PGRS | 2.200 |
| S2 | GHG Protocol na Prática para Empresas Brasileiras | Satélite informacional | GEE | 2.200 |
| S3 | RS para Crédito Bancário: BACEN 4.945 e PRSAC | Satélite transacional | RS | 2.000 |
| S4 | RELATÓRIO SETORIAL: Sustentabilidade na Indústria Alimentícia 2025 | Setorial público | Setoriais | 3.000 |

**Total**: ~9.400 palavras

#### Mês 8 — PARCERIAS: Nichos + Estadual + Contadores

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Contadores e Compliance Ambiental: Uma Parceria Necessária | Blog parceria | Blog | 2.000 |
| S2 | PGRS FEPAM Rio Grande do Sul | Satélite estadual | PGRS | 2.000 |
| S3 | Indicadores ESG para PMEs: Quais Medir e Como Reportar | Satélite informacional | RS | 2.200 |
| S4 | RELATÓRIO SETORIAL: Sustentabilidade na Saúde 2025 | Setorial público | Setoriais | 3.000 |

**Total**: ~9.200 palavras | **Bônus**: Segundo case study

#### Mês 9 — ATUALIZAÇÃO: Refresh Pilares + Nichos

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | **UPDATE**: PGRS Pilar (refresh dados, novas regulações) | Refresh pilar | PGRS | +500-1.000 |
| S2 | Inventário GEE para Eventos Corporativos | Satélite transacional | GEE | 1.800 |
| S3 | ESG para Licitações Públicas (Lei 14.133/2021) | Satélite transacional | RS | 1.800 |
| S4 | RELATÓRIO SETORIAL: Sustentabilidade no Agronegócio 2025 | Setorial público | Setoriais | 3.000 |

**Total**: ~7.100 palavras + refresh

#### Mês 10 — PROFUNDIDADE: Técnica Avançada + Último Estadual

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Fatores de Emissão MCTI 2025: Tabela Atualizada | Satélite informacional | GEE | 2.000 |
| S2 | PGRS IAT Paraná | Satélite estadual | PGRS | 2.000 |
| S3 | RS para Franqueados e Redes | Satélite transacional | RS | 1.800 |
| S4 | **UPDATE**: Inventário GEE Pilar (refresh SBCE, novos fatores) | Refresh pilar | GEE | +500-1.000 |

**Total**: ~6.300 palavras + refresh

#### Mês 11 — CONVERSÃO: Campanhas de Final de Ano

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Urgência: PGRS Renovação — Não Perca o Prazo em 2026 | Urgência/conversão | PGRS | 1.500 |
| S2 | Emissões GEE no Relatório de Sustentabilidade: Como Incluir Dados de 2025 | Informacional/conversão RS | GEE→RS | 1.800 |
| S3 | Bundle PGRS + RS: O Pacote Completo de Compliance para 2026 | Landing conversão | Cross | 1.200 |
| S4 | Retrospectiva Sustentabilidade PMEs 2025: O que Mudou | Blog awareness | Blog | 2.000 |

**Total**: ~6.500 palavras | **Bônus**: Terceiro case study

#### Mês 12 — PLANEJAMENTO: Consolidação + Ano 2

| Semana | Peça | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Preview: Regulação Ambiental 2026 — O que Esperar | Blog informacional | Blog | 2.000 |
| S2 | **UPDATE**: RS Pilar (refresh CVM, IFRS, novos indicadores) | Refresh pilar | RS | +500-1.000 |
| S3 | Anuário de Emissões PMEs 2025 (dados consolidados, PDF público) | Setorial/link bait | Setoriais | 3.500 |
| S4 | Revisão geral: auditoria de linkagem, redirect, GSC cleanup | Manutenção técnica | — | — |

**Total**: ~6.000 palavras + refresh + manutenção

### Resumo de Produção Anual

| Tipo | Quantidade | Palavras estimadas |
|---|---|---|
| Pilares (novos) | 3 (2 produto + 1 informacional GEE) | ~13.200 |
| Pilares (refresh) | 3 | ~2.000 |
| Satélites | 28 | ~58.000 |
| Blog (TOFU + comparativo + parceria) | 9 | ~18.000 |
| Relatórios setoriais | 5 | ~15.500 |
| Urgência regulatória | 3 | ~5.500 |
| Landing conversão | 1 | ~1.200 |
| Glossário | 1 hub + 60 termos | ~8.000 |
| Calendário regulatório | 1 | ~1.500 |
| PLG tools | 3 | N/A (interativos) |
| Case studies | 3 | ~3.000 |
| **TOTAL** | **~60 peças + 3 tools** | **~126.000 palavras** |

---

## 10. Sistema de Linkagem Interna

### 10 Regras de Linkagem

| # | Regra | Detalhamento |
|---|---|---|
| R1 | **Satélite → Pilar** (obrigatório) | Todo satélite linka para seu pilar na introdução. Anchor text com keyword do pilar. |
| R2 | **Pilar → Todos os satélites** | Pilar mantém seção hub com links para TODOS os satélites. Atualizar a cada publicação. |
| R3 | **Cross-cluster por relevância** | Satélites do mesmo segmento linkam entre si (ex: "PGRS Construtoras" ↔ "GEE Construtoras LEED"). |
| R4 | **Preços apenas no CTA final** | 1 link para `/precos/` por artigo, exclusivamente no CTA final. |
| R5 | **Setoriais bidirecional** | Setoriais ↔ satélites do mesmo segmento. |
| R6 | **Anchor text variado** | 40% keyword exata, 30% variação, 30% contextual. Nunca mesmo texto 2x para mesma URL. |
| R7 | **Min 3 links internos** | 1 pilar + 1 cross-cluster + 1 contextual. Max 8 links por 2.000 palavras. |
| R8 | **Estaduais → Pilar + Federal** | Link para pilar no 1o parágrafo + link para versão federal + "Veja também por estado". |
| R9 | **Glossário auto-link** | Max 3 glossary links por artigo. Nunca linkar em H1, H2 ou dentro de outros links. |
| R10 | **PLG tools → Cluster + Preços** | Cada ferramenta linka para pilar servido + `/precos/` no CTA pós-resultado + 2-3 satélites "próximos passos". |

### Mapa de Linkagem (diagrama)

```
                    ┌─────────────┐
                    │    HOME     │
                    └──────┬──────┘
                           │
          ┌────────────────┼────────────────┐
          │                │                │
    ┌─────▼─────┐   ┌─────▼─────┐   ┌─────▼─────┐
    │   /pgrs/  │◄──┤/inv-carb/ │◄──┤   /rs/    │
    │  (Pilar)  ├──►│  (Pilar)  ├──►│  (Pilar)  │
    └─────┬─────┘   └─────┬─────┘   └─────┬─────┘
          │                │                │
    ┌─────▼─────┐   ┌─────▼─────┐   ┌─────▼─────┐
    │ Satélites │   │ Satélites │   │ Satélites │
    │ (14+5est) │   │   (14)    │   │   (14)    │
    └─────┬─────┘   └─────┬─────┘   └─────┬─────┘
          │                │                │
          └───── CROSS-CLUSTER LINKS ───────┘
                           │
          ┌────────────────┼────────────────┐
          │                │                │
    ┌─────▼─────┐   ┌─────▼─────┐   ┌─────▼─────┐
    │/glossário/│   │/regulações│   │/setoriais/ │
    └───────────┘   └───────────┘   └────────────┘
          │                │                │
          └────────┬───────┘                │
                   ▼                        ▼
    ┌──────────┐ ┌──────────┐ ┌─────────┐ ┌────────┐
    │/ferramen │ │  /casos/  │ │ /preços/│ │ /sobre/│
    │  tas/    │ │          │ │         │ │        │
    └────┬─────┘ └──────────┘ └────▲────┘ └────────┘
         └─────────────────────────┘
           (CTA final de ferramentas)
```

---

## 11. SEO Técnico e Schema Markup

### 11.1 On-Page

**Title Tag**: Max 560px (NÃO 60 caracteres — português com acentos consome mais pixels). Keyword front-loaded nos primeiros 40 chars. Sem sufixo de marca em satélites.

**Meta Description**: Max 920px (~150-155 chars). Fórmula: problema + solução + CTA implícito. Sem ponto final.

**URLs**: Kebab-case sem acentos. Max 4 segmentos. Sem stopwords. Sem datas.

**Core Web Vitals Targets**:

| Métrica | Target | Estratégia |
|---|---|---|
| LCP | < 2.5s | SSG, `next/image` com priority no hero, font preload |
| INP | < 150ms | Debounce animações, `content-visibility: auto`, lazy-load modais |
| CLS | < 0.1 | Dimensões explícitas em imagens, font-display: swap com fallback |
| TTFB | < 600ms | Firebase Hosting CDN global, SSG puro |
| Lighthouse Mobile | >= 90 | Auditoria mensal, bundle analysis |

### 11.2 Schema Markup por Tipo de Página

| Tipo de Página | Schemas | Notas |
|---|---|---|
| Pilar (hub) | `Article` + `BreadcrumbList` + `HowTo` | **SEM FAQPage** (risco over-optimization) |
| Satélite | `Article` + `BreadcrumbList` + `FAQPage` (max 5) | FAQ schema apenas em satélites |
| `/precos/` | `Service` + `Offer` + `PriceSpecification` + `BreadcrumbList` | Um `Offer` por tier |
| `/sobre/` | `ProfessionalService` + `Organization` | Credenciais E-E-A-T |
| `/ferramentas/*` | `SoftwareApplication` + `BreadcrumbList` | applicationCategory: "BusinessApplication" |
| Home | `Organization` + `WebSite` com `SearchAction` | SearchAction após implementar busca |
| `/glossario/` | `DefinedTermSet` + `BreadcrumbList` | `DefinedTerm` por termo |
| `/regulacoes/` | `Article` + `BreadcrumbList` | `dateModified` crítico |
| `/casos/` | `Article` + `BreadcrumbList` | Social proof estruturado |
| Blog TOFU | `Article` + `BreadcrumbList` | Simples |

### 11.3 Schema JSON-LD Templates

**Article** (todos os artigos):
```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "{{title}}",
  "description": "{{metaDescription}}",
  "image": "https://{{domain}}/og/{{slug}}.png",
  "datePublished": "{{publishDate}}",
  "dateModified": "{{modifiedDate}}",
  "author": {
    "@type": "Person",
    "name": "{{authorName}}",
    "url": "https://{{domain}}/sobre/"
  },
  "publisher": {
    "@type": "Organization",
    "name": "{{brandName}}",
    "logo": { "@type": "ImageObject", "url": "https://{{domain}}/images/logo.png" }
  },
  "wordCount": "{{wordCount}}",
  "articleSection": "{{cluster}}"
}
```

**Service + Offer** (página `/precos/`):
```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "name": "Elaboração de PGRS",
  "description": "Plano de Gerenciamento de Resíduos Sólidos conforme Lei 12.305/2010",
  "provider": { "@type": "Organization", "name": "{{brandName}}" },
  "areaServed": { "@type": "Country", "name": "Brasil" },
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "itemListElement": [
      { "@type": "Offer", "name": "PGRS Standard", "description": "10 dias úteis",
        "priceSpecification": { "@type": "PriceSpecification", "price": "990.00", "priceCurrency": "BRL" } },
      { "@type": "Offer", "name": "PGRS Express", "description": "5 dias úteis",
        "priceSpecification": { "@type": "PriceSpecification", "price": "1490.00", "priceCurrency": "BRL" } },
      { "@type": "Offer", "name": "PGRS Urgente", "description": "48 horas",
        "priceSpecification": { "@type": "PriceSpecification", "price": "2490.00", "priceCurrency": "BRL" } }
    ]
  }
}
```

> Replicar estrutura para RS. GEE não tem página de preços.

### 11.4 Content Freshness Strategy

| Tier | Critério | Ação | Frequência |
|---|---|---|---|
| **Major Update** | >15% reescrito, nova seção | Atualizar `dateModified`, adicionar histórico, re-submeter GSC | Quando necessário |
| **Minor Update** | Links, typos, formatação | Atualizar `dateModified` apenas | Conforme necessidade |
| **Regulatory Trigger** | Nova lei/resolução/decreto | Atualizar em **72 horas**, destaque visual, alert box | Sob demanda |
| **Scheduled Review** | Revisão planejada | Verificar dados, links, CTAs, posição GSC | Pilares: semestral. Satélites: anual |

### 11.5 robots.txt

```
User-agent: *
Allow: /
Disallow: /api/
Disallow: /admin/
Disallow: /_next/
Disallow: /*?utm_*
Disallow: /*?draft=*
Disallow: /*?preview=*
Disallow: /*?ref=*

Sitemap: https://[dominio]/sitemap.xml
```

---

## 12. Funil de Conversão

### 12.1 Lead Magnets (1 por cluster)

| Cluster | Lead Magnet | Formato | Gate |
|---|---|---|---|
| **PGRS** | "Checklist: Sua empresa precisa de PGRS?" | PDF (3-5 pgs) — 15 perguntas sim/não, resultado "obrigado"/"recomendado"/"não aplicável" | Email + CNAE |
| **GEE** (educacional) | "Planilha: Calculadora simplificada de emissões CO2" | Google Sheets template copiável — inputs energia/combustível, output tCO2e | Email |
| **RS** | "Template: Modelo de Relatório GRI Simplificado" | DOCX (10-15 pgs) — estrutura GRI 2021 adaptada para PMEs com instruções | Email + CNAE |

**Regras**: Gate leve (3 campos: nome + email + setor/CNAE). Entrega imediata. Follow-up inicia nurture sequence. Design profissional com marca.

### 12.2 Conversion Paths (3 caminhos)

**Path 1 — Cold** (visitante informacional):
```
Artigo TOFU/MOFU → CTA lead magnet → Download (email + CNAE)
  → Email nurture (5-7 emails, 14-21 dias)
    → "Agende consulta gratuita de 15 min"
      → Calendly/WhatsApp → Diagnóstico → Proposta
Timeline: 14-30 dias | CVR: 1-3% artigo→lead, 5-10% lead→consulta
```

**Path 2 — Warm** (visitante com intenção comercial):
```
Página de preços OU "quanto custa" → CTA "Fale com especialista"
  → WhatsApp pré-preenchido com serviço + tier
    → Conversa diagnóstica (5-10 min)
      → Proposta em 24h → Follow-up 48h
Timeline: 1-7 dias | CVR: 3-8% pricing→WhatsApp, 20-40% WhatsApp→proposta
```

**Path 3 — Hot** (visitante com urgência):
```
Artigo urgência/multa/prazo → CTA "Regularize em 5 dias úteis"
  → WhatsApp direto (urgência) → Diagnóstico mesmo dia
    → Proposta Express/Urgente em 2h → Fechamento 24-48h
Timeline: 0-48h | CVR: 5-15% artigo→WhatsApp, 30-50% WhatsApp→fechamento
```

### 12.3 Email Nurture Sequences

#### Sequência PGRS (7 emails, 21 dias)

| # | Dia | Assunto | CTA |
|---|---|---|---|
| 1 | 0 | Seu checklist PGRS está aqui | Download checklist |
| 2 | 3 | A multa por falta de PGRS chega a R$50 milhões | Ler artigo multas |
| 3 | 7 | Como saber qual profissional assina seu PGRS | Ler artigo credenciais |
| 4 | 10 | O que órgãos ambientais realmente exigem | Ler pilar PGRS |
| 5 | 14 | Quanto custa um PGRS (e quanto custa NÃO ter) | Ver preços |
| 6 | 18 | Como [empresa X] regularizou em 10 dias | Agendar consulta |
| 7 | 21 | Última chance: diagnóstico gratuito | WhatsApp/Calendly |

#### Sequência GEE (5 emails, 14 dias) — REDIRECIONA PARA RS

> **v2.1**: Sequência mantida para leads que usaram a calculadora GEE. Objetivo: educar sobre emissões e converter para RS.

| # | Dia | Assunto | CTA |
|---|---|---|---|
| 1 | 0 | Sua planilha de emissões está pronta | Acessar planilha |
| 2 | 3 | Lei 15.042/2024: o que muda para sua empresa | Ler artigo SBCE |
| 3 | 7 | Escopos 1, 2 e 3: por que seu cliente já está perguntando | Ler artigo escopos |
| 4 | 10 | Seus dados de emissões valem mais dentro de um RS | Ver preços RS |
| 5 | 14 | Vamos montar seu RS com dados de emissões? | WhatsApp/Calendly |

#### Sequência RS (5 emails, 14 dias)

| # | Dia | Assunto | CTA |
|---|---|---|---|
| 1 | 0 | Seu template GRI simplificado está aqui | Download template |
| 2 | 3 | CVM 193/2023: o efeito cascata já chegou | Ler artigo CVM |
| 3 | 7 | O relatório que abre portas: crédito, licitações, grandes clientes | Ler pilar RS |
| 4 | 10 | Do template ao relatório profissional: o que muda | Ver preços RS |
| 5 | 14 | Vamos montar seu relatório juntos? | WhatsApp/Calendly |

**Digest Regulatório Mensal**: Para todos os subscribers — 3-5 novidades do mês + links para artigos.

### 12.4 WhatsApp Integration

- **Botão flutuante** em todas as páginas: aparece após 5s ou 30% scroll
- **Mensagens pré-preenchidas** por origem (produto, preços, urgência, ferramenta)
- **Mobile**: Click-to-call no header, botão WhatsApp 48x48px, sticky CTA bar bottom

### 12.5 Lead Scoring

| Ação | Pontos |
|---|---|
| Visitou artigo TOFU | +5 |
| Visitou artigo MOFU/BOFU | +10 |
| Visitou página de preços | +20 |
| Visitou preços 2x+ | +15 (adicional) |
| Baixou lead magnet | +15 |
| Usou ferramenta/calculadora | +20 |
| Clicou "Contratar" ou "Solicitar" | +25 |
| Enviou formulário | +30 |
| Inatividade >30 dias | -20 |

| Faixa | Score | Ação |
|---|---|---|
| **Cold** | 1-30 | Email nurture. Nenhum contato direto. |
| **Warm** | 31-70 | Email personalizado + WhatsApp em 24h. |
| **Hot** | 71-100 | WhatsApp em 2h. Ligação no mesmo dia. Proposta personalizada. |

### 12.6 A/B Testing Framework

| Prioridade | Teste | Métrica |
|---|---|---|
| 1 | CTA copy | CTR no botão |
| 2 | CTA placement | Clicks por sessão |
| 3 | Lead magnet offer | Taxa de download |
| 4 | Pricing layout | Tempo na página + click tier |
| 5 | Social proof | Conversão form/WhatsApp |
| 6 | Form length | Taxa de submissão |

Ferramenta: **PostHog** (free tier, 1M eventos/mês). Mínimo 200 conversões por variante. 1 teste por vez por página. Duração mínima 14 dias.

---

## 13. Amplificação de Conteúdo e Backlinks

### 13.1 Estratégia de Backlinks Orgânicos

| Tática | Tipo de conteúdo | Meta backlinks/mês |
|---|---|---|
| **Relatórios setoriais** com dados exclusivos | PDFs públicos + página web | 3-5 (M6+) |
| **Calendário regulatório** como recurso de referência | Página visual atualizada | 2-3 (M3+) |
| **Glossário** como fonte de definições | 60+ termos indexáveis | 1-2 (contínuo) |
| **Anuário PMEs** (M12) | PDF consolidado — principal link bait | 5-10 |
| **Dados citáveis** em artigos (tabelas de multas, limiares, custos) | Tabelas estruturadas | 1-2 (contínuo) |

### 13.2 Distribuição de Conteúdo

| Canal | Formato | Frequência |
|---|---|---|
| **LinkedIn** (perfil fundador) | Posts curtos (300-500 palavras) + link para artigo | 3x/semana |
| **LinkedIn** (página empresa) | Carrosséis com dados + infográficos | 1x/semana |
| **Newsletter** (Brevo) | Digest regulatório + artigo destaque | 1x/mês |
| **WhatsApp** (grupos setoriais) | Dicas curtas com link para artigo | 2x/semana |
| **Google Business Profile** | Posts com link para conteúdo | 1x/semana |

### 13.3 Parcerias para Backlinks

| Parceiro | Abordagem | Resultado esperado |
|---|---|---|
| Blogs de contabilidade | Guest post sobre compliance ambiental para clientes contábeis | Backlink contextual + referral traffic |
| Portais de notícias regionais | Press release sobre relatórios setoriais com dados exclusivos | Backlinks de alta autoridade |
| Universidades | Conteúdo como referência bibliográfica em cursos de eng. ambiental | Backlinks .edu |
| CRQ/CREA regionais | Material educacional linkado em páginas de orientação | Backlinks institucionais |

---

## 14. KPIs e Sistema de Monitoramento

### 14.1 KPIs Orgânicos (SEO)

| KPI | Mês 3 | Mês 6 | Mês 12 | Fonte |
|---|---|---|---|---|
| Posição média GSC (keywords target) | Top 20 pilares | Top 10 | Top 3 prioritárias | GSC |
| Impressões orgânicas | 5.000+ | 25.000+ | 100.000+ | GSC |
| Cliques orgânicos | 300+ | 1.500+ | 6.000+ | GSC |
| CTR médio | >3% | >4% | >5% | GSC |
| Páginas indexadas | 20+ | 45+ | 80+ | GSC |
| Backlinks (domínios únicos) | 5+ | 20+ | 60+ | Ahrefs |
| Tempo médio na página | 2min+ | 3min+ | 3.5min+ | GA4 |

### 14.2 KPIs de Conversão

| KPI | Mês 3 | Mês 6 | Mês 12 | Fonte |
|---|---|---|---|---|
| Leads orgânicos/mês | 3 | 30 | 180 | GA4 + Firestore |
| Leads total (todos canais)/mês | 15+ | 60+ | 250+ | Firestore |
| Lead magnet downloads/mês | 10+ | 40+ | 120+ | Brevo |
| Email open rate | >25% | >30% | >30% | Brevo |
| WhatsApp clicks/mês | 20+ | 80+ | 200+ | PostHog |
| Form submissions/mês | 5+ | 25+ | 80+ | Firestore |

> **Nota matemática corrigida**: 300 cliques/mês com CVR de 1% = 3 leads, não 10. Leads significativos via SEO só a partir do Mês 6+. Por isso, multi-channel é essencial desde o Dia 1.

### 14.3 KPIs de Receita

| KPI | Mês 3 | Mês 6 | Mês 12 | Fonte |
|---|---|---|---|---|
| MQL/mês | 10+ | 40+ | 150+ | Lead scoring |
| MQL→SQL rate | 30%+ | 40%+ | 50%+ | CRM/Firestore |
| SQL→Cliente rate | 20%+ | 25%+ | 30%+ | CRM/Firestore |
| Ticket médio | R$1.200 | R$1.400 | R$1.600 | Financeiro |
| Receita mensal | **R$7.000** | **R$18.000** | **R$55.000** | Financeiro |
| Receita recorrente (renovações) | R$0 | R$500 | R$5.000 | Financeiro |
| CAC médio | R$200 | R$150 | R$100 | Financeiro |
| LTV/CAC ratio | 4x+ | 6x+ | 10x+ | Financeiro |

### 14.4 KPIs Multi-Channel

| KPI | Mês 3 | Mês 6 | Mês 12 |
|---|---|---|---|
| Leads outbound (contadores) | 5+ | 15+ | 30+ |
| Leads Google Ads | 5+ | 15+ | 40+ |
| Leads marketplace | 3+ | 8+ | 15+ |
| Leads partner referral | 0 | 5+ | 20+ |
| Google Ads ROAS | 2x+ | 3x+ | 4x+ |

### 14.5 Rotina de Monitoramento

| Frequência | Duração | Atividades |
|---|---|---|
| **Diária** | 5 min | Erros indexação GSC, notificações leads hot, uptime |
| **Semanal** | 20 min | Top 10 keywords, leads novos, lead scoring review, 404s |
| **Mensal** | 1h | Relatório completo (impressões, cliques, CTR, leads por UTM), A/B tests, email performance, revenue breakdown |
| **Trimestral** | 3h | Auditoria linkagem (Screaming Frog), update pilares, revisão CTAs, análise canibalização |
| **Semestral** | 1 dia | Re-pesquisa keywords, mapeamento regulatório, auditoria concorrentes, revisão estratégia |

---

## 15. Stack Técnico

### 15.1 Ferramentas SEO/Marketing (R$0-1.000/mês)

| Ferramenta | Função | Custo |
|---|---|---|
| Google Search Console | Indexação, posições, CTR | R$0 |
| Google Analytics 4 | Tráfego, conversões, comportamento | R$0 |
| Google Keyword Planner | Pesquisa de keywords, volume | R$0 |
| Ahrefs Webmaster Tools | Backlinks, saúde do site | R$0 |
| Screaming Frog (free) | Auditoria técnica (500 URLs) | R$0 |
| PageSpeed Insights | Core Web Vitals, Lighthouse | R$0 |
| **Brevo** (free tier) | Email marketing, automação, 300 emails/dia | R$0 |
| **PostHog** (free tier) | A/B testing, analytics, 1M eventos/mês | R$0 |
| **WhatsApp Business** | Canal de conversão direto | R$0 |
| Google Ads (opcional) | Campanhas high-intent | R$500-1.000/mês |

### 15.2 Stack de Desenvolvimento

| Componente | Tecnologia | Justificativa |
|---|---|---|
| Framework | **Next.js 15 (App Router)** | Server Components, `generateMetadata`, SSG |
| Content | **MDX no repo** (`@next/mdx`) | Git versioning, R$0, sem vendor lock-in |
| Styling | **Tailwind CSS** | Utility-first, purge automático, CSS mínimo |
| Hosting | **Firebase Hosting** | CDN global (151+ PoPs), free tier generoso |
| Dynamic routes | **Cloud Functions for Firebase** | OG images, form handling, lead notifications |
| OG Images | **satori + sharp** (via Cloud Function) | JSX→SVG→PNG sem Vercel |
| SEO Metadata | **Built-in Metadata API** | NÃO usar next-seo (redundante no App Router) |
| JSON-LD | **Custom `<JsonLd>` Server Component** | Zero bundle size, tipado TypeScript |
| Sitemap | **next-sitemap** | `lastmod` do frontmatter, sitemap index |
| Search | **Pagefind** (M4+) | Índice estático, stemming português, ~50KB client |
| Email | **Brevo** (free tier) | 300 emails/dia, workflows automação, API REST |
| A/B Testing | **PostHog** (free tier) | Feature flags server-side, session replay |
| Forms | **Firebase Firestore** | Serverless via Cloud Function, realtime |
| Monitoring | **Firebase Performance** | Web Vitals automáticos, custom traces |

### 15.3 Estrutura do Projeto

```
paloma/
├── .github/workflows/
│   ├── deploy.yml               # Push to main → build → firebase deploy
│   ├── lighthouse-ci.yml        # Lighthouse em PRs
│   ├── content-quality.yml      # Validação MDX em pushes
│   └── broken-links.yml         # Cron semanal link checker
├── app/
│   ├── layout.tsx               # Root: fonts, analytics, nav, footer
│   ├── page.tsx                 # Home (SSG)
│   ├── sitemap.ts               # Programático
│   ├── robots.ts                # Programático
│   ├── pgrs/                    # Pilar + [slug] satélites
│   ├── inventario-carbono/      # Pilar + [slug] satélites (informacional)
│   ├── relatorio-sustentabilidade/ # Pilar + [slug] satélites
│   ├── precos/                  # Pricing (SSG)
│   ├── glossario/               # Glossário com anchors
│   ├── regulacoes/              # Timeline regulatória
│   ├── casos/                   # Case studies
│   ├── ferramentas/             # PLG tools (SSG + client JS)
│   ├── setoriais/               # Relatórios setoriais
│   ├── blog/                    # TOFU + cross-cluster
│   ├── sobre/                   # Institucional + E-E-A-T
│   └── obrigado/                # Thank-you page pós-form
├── content/                     # MDX (Git-managed)
│   ├── pgrs/                    # Pilar + satélites
│   ├── inventario-carbono/      # Pilar + satélites
│   ├── relatorio-sustentabilidade/
│   ├── setoriais/
│   ├── blog/
│   ├── casos/
│   └── glossario/termos.json
├── components/
│   ├── mdx/                     # CTA, FAQ, InfoBox, ProofBox, TOC, etc.
│   ├── layout/                  # Header, Footer, Breadcrumbs, WhatsApp
│   ├── ui/                      # Button, Badge, Card, Modal
│   ├── forms/                   # IntakeForm, LeadMagnetGate
│   └── seo/                     # JsonLd, SchemaTemplates
├── lib/                         # content.ts, schema.ts, metadata.ts, glossary.ts
├── functions/                   # Cloud Functions
│   └── src/                     # ogImage, formHandler, leadScorer, rebuildTrigger
├── public/
│   ├── images/
│   └── downloads/               # Lead magnets, relatórios setoriais
├── scripts/                     # validate-content, generate-search-index
├── firebase.json
├── next.config.ts
├── tailwind.config.ts
└── middleware.ts                 # X-Robots-Tag, redirects
```

### 15.4 Deploy Pipeline

```
Content update (push MDX) → GitHub Actions → next build → firebase deploy → CDN atualizado
                                                                              (~3-5 min total)
```

- **CI**: Validação MDX (frontmatter, word count, links), Lighthouse CI em PRs
- **Quality gates**: Performance >= 90, Accessibility >= 95, SEO >= 98
- **Broken link checker**: Cron semanal (GitHub Actions + lychee)

---

## 16. SOP de Produção

### 16.1 Processo de Criação de Artigo

| Fase | Duração | Atividades | Entregável |
|---|---|---|---|
| 1. **Brief** | 30 min | Preencher frontmatter completo, definir H2s, escolher CTAs, identificar regulações | Brief aprovado |
| 2. **Pesquisa** | 1-2h | Verificar legislação atual, buscar dados de fontes oficiais, analisar concorrentes top 3 | Notas de pesquisa |
| 3. **Redação** | 3-5h | Escrever seguindo template de 14 blocos, inserir componentes MDX | Rascunho MDX |
| 4. **Revisão SEO** | 30 min | Verificar keyword density, links internos, title/meta medidos por pixel | Checklist SEO |
| 5. **Revisão técnica (RT)** | 1-2h | RT verifica precisão regulatória, assina review | Badge E-E-A-T |
| 6. **Publicação** | 15 min | Push no main, deploy automático, submeter GSC | Artigo live |
| 7. **Distribuição** | 30 min | LinkedIn post, newsletter se aplicável, WhatsApp groups | Social proof |

**Tempo total por artigo**: 6-10h (satélite) / 12-16h (pilar)
**Capacidade**: 1 pessoa produz 4-5 peças/mês

### 16.2 Checklist de Qualidade (obrigatório antes do push)

- [ ] Frontmatter 100% preenchido (todos os campos obrigatórios)
- [ ] Word count >= mínimo do tipo (pilar 3.500, satélite 1.800, blog 1.500)
- [ ] Title tag medido por pixel (max 560px)
- [ ] Meta description medida por pixel (max 920px)
- [ ] Keyword principal nos primeiros 100 chars da introdução
- [ ] Min 3 links internos (1 pilar + 1 cross-cluster + 1 contextual)
- [ ] Min 3 referências a fontes oficiais
- [ ] Badge E-E-A-T presente (nome do RT + registro)
- [ ] CTA mid-article linka para pilar ou ferramenta (NUNCA preços)
- [ ] CTA final linka para preços ou WhatsApp
- [ ] Max 3 glossary links
- [ ] FAQ max 5 perguntas (apenas satélites)
- [ ] Imagens com alt text descritivo
- [ ] URLs sem acentos, kebab-case, max 4 segmentos

---

## 17. Projeções de Receita

### 17.1 Cenário A — Content-Only (apenas SEO orgânico)

| Mês | Tráfego Org. | CVR | Leads | Close Rate | Ticket Médio | Receita |
|---|---|---|---|---|---|---|
| 1 | 50 | 0.5% | 0 | - | - | R$0 |
| 2 | 150 | 0.5% | 1 | 20% | R$990 | R$200 |
| 3 | 300 | 1% | 3 | 20% | R$1.100 | R$660 |
| 6 | 1.500 | 1.5% | 23 | 22% | R$1.200 | R$6.072 |
| 9 | 3.500 | 2% | 70 | 25% | R$1.300 | R$22.750 |
| 12 | 6.000 | 2.5% | 150 | 28% | R$1.400 | R$58.800 |

**Receita acumulada 12 meses**: ~R$140.000 | **Break-even**: Mês 5-6

### 17.2 Cenário B — Multi-Channel (RECOMENDADO)

| Mês | Leads Org. | Outbound | Ads | PLG | Mktplace | Partner | Total | Close Rate | Ticket | Receita |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | 0 | 3 | 5 | 0 | 2 | 0 | 10 | 20% | R$1.100 | R$2.200 |
| 2 | 0 | 5 | 8 | 2 | 3 | 0 | 18 | 22% | R$1.150 | R$4.554 |
| 3 | 3 | 8 | 10 | 5 | 4 | 2 | 32 | 22% | R$1.200 | R$8.448 |
| 6 | 23 | 15 | 15 | 12 | 6 | 8 | 79 | 25% | R$1.300 | R$25.675 |
| 9 | 50 | 18 | 18 | 18 | 8 | 15 | 127 | 27% | R$1.400 | R$47.998 |
| 12 | 150 | 20 | 20 | 25 | 10 | 25 | 250 | 30% | R$1.500 | R$112.500 |

**Receita acumulada 12 meses**: ~R$380.000 | **Break-even**: Mês 1-2

### 17.3 Comparativo

| Métrica | Cenário A (Content-Only) | Cenário B (Multi-Channel) |
|---|---|---|
| Receita Mês 3 | R$660 | **R$8.448** |
| Receita Mês 6 | R$6.072 | **R$25.675** |
| Receita Mês 12 | R$58.800 | **R$112.500** |
| Receita acumulada 12m | R$140.000 | **R$380.000** |
| Break-even | Mês 5-6 | **Mês 1-2** |
| Risco caixa negativo | Alto (M1-5) | Baixo |
| Investimento mensal Ads | R$0 | R$500-1.000 |

> **Recomendação**: Cenário B. O investimento adicional de R$500-1.000/mês em Ads se paga no primeiro lead convertido. Outbound e marketplaces são custo zero além de tempo.

---

## 18. Gestão de Riscos

| # | Risco | Prob. | Impacto | Mitigação | Trigger |
|---|---|---|---|---|---|
| 1 | **AI Overviews canibalizam cliques orgânicos** | Alta (60%) | Médio | Conteúdo focado em transação. PLG tools que exigem interação. Schema robusto. Diversificar canais. | CTR orgânico cai >20% em 2 meses |
| 2 | **Entrada de concorrente VC-backed** | Média (40%) | Alto | First-mover em nicho PME. Relacionamento com contadores. Preços que VC não sustenta. | Concorrente com >R$1M investido |
| 3 | **Mudança regulatória major** | Alta (70%) | Médio-Alto | Content freshness (72h update). Monitoramento DOU semanal. RT com acesso a previews. | Nova regulação publicada |
| 4 | **Bottleneck de capacidade** | Média (30%) | Alto | Rede de engenheiros parceiros. Tiers de entrega. Waitlist transparente. Priorizar bundle. | Lead time excede 15 dias |
| 5 | **RT sai / não encontrado** | Média (40%) | Crítico | 2-3 engenheiros parceiros. Contrato com transição 60 dias. Fee por documento (não retainer). | RT informa saída |
| 6 | **Google penalty** | Baixa (15%) | Alto | E-E-A-T rigoroso. Sem conteúdo thin. FAQ limitado. Audit trimestral. Diversificar tráfego. | Queda >50% orgânico em 1 semana |
| 7 | **Brevo/PostHog mudam free tier** | Baixa (10%) | Baixo | Exportar dados. Alternativas mapeadas (Mailchimp, Plausible). | Anúncio de pricing |
| 8 | **PMEs não percebem valor** | Média (35%) | Alto | TOFU educacional. Framing "quanto custa NÃO ter". Calculadora ROI. Cases reais. | CVR < 0.5% após 3 meses |

---

## 19. Síntese Estratégica e Próximos Passos

### 19.1 Resumo Executivo

A Paloma é uma plataforma B2B de compliance ambiental para PMEs brasileiras com:
- **2 produtos** (PGRS + Relatório de Sustentabilidade) — GEE removido como produto, mantido para SEO
- **Modelo híbrido** (self-service + done-for-you) com revisão por RT habilitado
- **7 canais** de aquisição desde o Dia 1 — não depende apenas de SEO
- **51+ peças** de conteúdo em 12 meses (126.000 palavras)
- **3 PLG tools** para captura automatizada de leads
- **Projeção multi-channel**: ~R$380K em 12 meses com break-even no Mês 1-2

### 19.2 Próximos Passos Imediatos (Semana 1)

| # | Ação | Prazo | Bloqueio | Entregável |
|---|---|---|---|---|
| 1 | **Resolver RT** — Contatar 5 engenheiros ambientais freelance (fee-por-documento) | Dia 1-3 | **BLOQUEIA tudo** | Carta de intenção com 1+ RT |
| 2 | **Definir modelo de receita** — Tiers + preços + modelo documentado | Dia 1-2 | — | Documento 1 página |
| 3 | **Configurar repo** — Next.js 15 + App Router + Tailwind + Firebase Hosting | Dia 1-3 | — | Site live com placeholder |
| 4 | **WhatsApp Business** — Número dedicado, auto-reply, catálogo | Dia 2 | — | WhatsApp ativo |
| 5 | **Componente WhatsApp** — Floating button com mensagens pré-preenchidas | Dia 3-4 | #3 | Componente deployado |
| 6 | **Outbound contadores** — Lista 20 escritórios (BH + SP), email frio | Dia 3-5 | #2 | 20 emails enviados |
| 7 | **Marketplaces** — Perfis em GetNinjas + Workana | Dia 3-4 | #2 | Perfis ativos |
| 8 | **Lead magnet PGRS** — Checklist PDF (3-5 páginas, Canva) | Dia 4-5 | — | PDF pronto |
| 9 | **Configurar Brevo** — Listas, template base, formulário, 1 automação | Dia 4-5 | — | Brevo configurado |
| 10 | **Artigo urgência SBCE** — Primeiro conteúdo publicado | Dia 5-7 | **#1** (RT) | Artigo live + GSC |
| 11 | **Google Ads** — Conta, 5-10 keywords high-intent, R$30/dia | Dia 5-7 | #3 | Campanha ativa |
| 12 | **PostHog** — SDK, eventos básicos (page_view, cta_click, form_submit) | Dia 5-7 | #3 | Analytics ativo |

### 19.3 Checkpoints

**Checkpoint Semana 1**: RT parceiro confirmado, site no ar (placeholder), WhatsApp ativo, 20 contadores contactados, Brevo configurado, primeiro artigo em produção.

**Checkpoint Semana 2**: Primeiro artigo publicado, Google Ads rodando, 2+ leads de marketplace/outbound, lead magnet disponível, PostHog trackeando.

**Checkpoint Mês 1**: 3 pilares publicados + 1 urgência + 1 PLG tool, 10+ leads totais, RT confirmado com pelo menos 1 documento entregue.

**Checkpoint Mês 3**: 15+ peças publicadas, 32+ leads/mês (multi-channel), R$8.000+ receita mensal, 3+ parceiros contadores ativos, top 20 GSC para keywords pilar.

**Checkpoint Mês 6**: 33+ peças, top 10 GSC, R$18.000+/mês, 2+ case studies, 15+ parceiros.

**Checkpoint Mês 12**: 51+ peças, top 3 GSC prioritárias, R$55.000+/mês, 30% receita de renovações, produto GEE em avaliação para lançamento.

---

> **Documento confidencial — Paloma v2.1** | Incorpora feedback da especialista técnica (remoção GEE como produto) + 50+ recomendações do painel de 6 especialistas | Abril 2026
