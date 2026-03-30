# PLANO DE CONTEUDO SEO v2.0 — Plataforma de Sustentabilidade para PMEs

**Versao**: 2.0 | **Data**: 2026-03-30 | **Horizonte**: 12 meses | **Status**: Reescrita completa pos-revisao cascateada (6 especialistas)
**Hosting**: Firebase Hosting | **Stack**: Next.js 15 App Router + MDX + SSG + Cloud Functions
**Cadencia**: 5 pecas/mes (M1-M3) → 4 pecas/mes (M4-M12) | **Total**: 51 pecas em 12 meses

---

## 1. VISAO ESTRATEGICA v2.0

### 1.1 Posicionamento

Plataforma B2B de compliance ambiental para PMEs brasileiras. Tres produtos core — PGRS, Inventario de Carbono GEE, Relatorio de Sustentabilidade — entregues via modelo hibrido (self-service online + done-for-you para casos complexos).

**Diferencial competitivo**: Unica plataforma que combina geracao automatizada de documentos com revisao por Responsavel Tecnico habilitado (ART assinada), a precos acessiveis para PMEs.

### 1.2 Os 4 Pilares Estrategicos

| # | Pilar | Descricao | Metrica-chave |
|---|---|---|---|
| 1 | **Topical Authority** | Dominio como referencia mais completa do Brasil sobre sustentabilidade para PMEs. Cobertura exaustiva de regulacoes federais e estaduais. | Posicao media GSC, impressoes organicas |
| 2 | **Conversao Inteligente** | Cada peca de conteudo tem papel definido no funil. CTAs calibrados por estagio. Lead magnets, PLG tools e nurture sequences integrados ao fluxo editorial. | Taxa conversao conteudo→lead, leads qualificados/mes |
| 3 | **Autonomia Editorial** | Processos documentados, templates rigidos, SOP de producao. Escalavel com equipe minima (1 pessoa produz 4-5 pecas/mes). | Tempo medio por peca, consistencia de qualidade |
| 4 | **Go-to-Market Multi-Canal** | Conteudo e Channel #2. Outbound para contadores e Channel #1. PLG tools, Google Ads e parcerias aceleram receita nos primeiros 90 dias. | Receita por canal, CAC por canal |

### 1.3 E-E-A-T Corrigido

**BLOQUEADOR RESOLVIDO**: Todo conteudo tecnico (PGRS, GEE, RS) exige Responsavel Tecnico (RT) habilitado com ART. Sem RT, a plataforma configura exercicio ilegal da profissao.

**Modelo de autoria**:

| Elemento | Responsavel | Onde aparece |
|---|---|---|
| **Autor principal** | Fundador(a) — nome, foto, bio, LinkedIn | Byline de todos os artigos |
| **Revisor tecnico** | RT contratado (CRQ/CREA/CRBio conforme tipo) | Badge "Revisado por [Nome], [Registro]" no topo e rodape |
| **Credenciais exibidas** | ART do profissional, registro no conselho, formacao | Pagina `/sobre/` + schema ProfessionalService |
| **Historico de atualizacoes** | Automatico via frontmatter MDX | Rodape dos pilares: "Publicado em X, atualizado em Y" |

**Opcoes de contratacao do RT** (decisao do fundador):
1. Retainer mensal: ~R$2.000-3.000/mes (melhor para volume)
2. Fee por documento: R$200-500/ART (viavel no inicio com <10 documentos/mes)
3. Parceria com engenheiro ambiental freelance: 30% do valor do servico

### 1.4 Modelo de Receita: HIBRIDO

Duas lanes explicitas em toda a comunicacao e na pagina de precos:

**Lane A — Self-Service Online**
- Cliente preenche questionario guiado na plataforma
- Documento gerado automaticamente + revisado por RT
- Checkout online, preco fixo por tier
- CTA: "Contratar agora", "Gerar meu PGRS"
- Ideal para: PGRS simples, renovacoes, PMEs com <50 funcionarios

**Lane B — Done-for-You (Consultoria)**
- Levantamento presencial/remoto por especialista
- Documento elaborado sob medida + ART
- Proposta personalizada via WhatsApp/email
- CTA: "Fale com especialista", "Solicitar proposta"
- Ideal para: PGRSS, PGRCC complexos, inventarios GEE com multiplas unidades, RS com GRI

**Pricing Tiered (Lane A)**:

| Tier | PGRS | GEE | RS | Bundle Completo |
|---|---|---|---|---|
| Standard (10 dias uteis) | R$990 | R$1.290 | R$1.490 | R$2.990 |
| Express (5 dias uteis) | R$1.490 | R$1.790 | R$1.990 | R$4.290 |
| Urgente (48h) | R$2.490 | R$2.990 | R$2.990 | R$6.990 |
| Renovacao anual | R$490 | R$690 | R$790 | R$1.490 |

### 1.5 Go-to-Market Multi-Canal

| Canal | Prioridade | Inicio | Investimento | Receita estimada M3 |
|---|---|---|---|---|
| **#1 Outbound contadores** | P0 | Semana 1 | R$0 (tempo) | R$3.000-5.000 |
| **#2 Conteudo SEO** | P0 | Semana 1 | R$0 (tempo) | R$890-1.500 |
| **#3 Google Ads** | P1 | Mes 1 | R$500-1.000/mes | R$1.500-3.000 |
| **#4 PLG tools** | P1 | Mes 1 | R$0 (dev time) | R$500-1.000 (leads) |
| **#5 Marketplaces** | P2 | Mes 1 | R$0 | R$500-1.000 |
| **#6 Parcerias (advocacia, ISO)** | P2 | Mes 2-3 | R$0 | R$500-1.500 |
| **#7 LinkedIn organic** | P1 | Mes 1 | R$0 (tempo) | Brand awareness |

**Parcerias — Cronograma Corrigido** (movido de Mes 8 para Mes 1):

| Parceiro | Modelo | Quando |
|---|---|---|
| Contadores e escritorios contabeis | 15-20% comissao por indicacao | Semana 1 |
| Engenheiros ambientais freelance | 30% (executam trabalho tecnico) | Semana 1 |
| Advocacia ambiental | 15% referral fee | Mes 2 |
| Consultorias ISO 14001 | White-label com 40% desconto | Mes 4 |
| Associacoes (FIEMG, FIESP, FIRJAN) | Pricing institucional | Mes 3 |

---

## 2. ARQUITETURA DO SITE v2.0

### 2.1 Mapa de URLs Completo

```
/                                          # Home (SSG, rebuild on deploy)
│
├── /pgrs/                                 # PILAR — Guia Completo PGRS
│   ├── /pgrs/[slug]/                      # Satelites PGRS (12+)
│   ├── /pgrs/precos/                      # Precos especificos PGRS
│   ├── /pgrs/pgrs-cetesb-sao-paulo/       # Estadual SP
│   ├── /pgrs/pgrs-feam-minas-gerais/      # Estadual MG
│   ├── /pgrs/pgrs-inea-rio-de-janeiro/    # Estadual RJ
│   ├── /pgrs/pgrs-fepam-rs/              # Estadual RS
│   └── /pgrs/pgrs-iat-parana/            # Estadual PR
│
├── /inventario-carbono/                   # PILAR — Guia Completo GEE
│   ├── /inventario-carbono/[slug]/        # Satelites GEE (12+)
│   └── /inventario-carbono/precos/        # Precos especificos GEE
│
├── /relatorio-sustentabilidade/           # PILAR — Guia Completo RS
│   ├── /relatorio-sustentabilidade/[slug]/ # Satelites RS (12+)
│   └── /relatorio-sustentabilidade/precos/ # Precos especificos RS
│
├── /precos/                               # Pagina unificada de precos (todas as lanes)
│
├── /glossario/                            # 50-80 termos de sustentabilidade
│   └── /glossario/[termo]/               # Pagina individual por termo (definicao + links)
│
├── /regulacoes/                           # Timeline visual regulatoria
│   └── /regulacoes/[slug]/               # Pagina dedicada por regulacao
│
├── /casos/                                # Case studies / depoimentos
│   └── /casos/[slug]/                     # Case individual
│
├── /ferramentas/                          # PLG tools (lead capture)
│   ├── /ferramentas/autodiagnostico/      # Quiz compliance
│   ├── /ferramentas/calculadora-emissoes/ # Calculadora GEE
│   └── /ferramentas/gerador-pgrs/         # Gerador PGRS basico
│
├── /setoriais/                            # Relatorios setoriais publicos (PDF + pagina)
│   └── /setoriais/[slug]/                 # Relatorio individual
│
├── /blog/                                 # TOFU + cross-cluster + awareness
│   └── /blog/[slug]/                      # Post individual
│
├── /sobre/                                # Institucional + E-E-A-T + equipe
├── /contato/                              # Formulario de intake + WhatsApp
│
├── /sitemap.xml                           # Programatico (app/sitemap.ts)
├── /robots.txt                            # Programatico (app/robots.ts)
└── /rss.xml                               # Feed RSS para newsletters
```

### 2.2 Estrategia de Precos nas URLs

**Abordagem hibrida** (resolve canibalizacao B4.1 da revisao):

| URL | Funcao | Conteudo |
|---|---|---|
| `/precos/` | Hub unificado de conversao | Tabela comparativa dos 3 produtos, tiers, FAQ de precos, CTA checkout/WhatsApp |
| `/pgrs/precos/` | Landing especifica PGRS | Detalhamento do que inclui cada tier PGRS, comparativo mercado, CTA direto |
| `/inventario-carbono/precos/` | Landing especifica GEE | Idem para GEE |
| `/relatorio-sustentabilidade/precos/` | Landing especifica RS | Idem para RS |
| `/pgrs/quanto-custa-pgrs/` | Artigo educacional | Fatores de custo, faixas de mercado, comparacoes — SEM tabela de precos propria, linka para `/pgrs/precos/` |

**Regra**: Artigos "quanto custa" sao educacionais sobre fatores/mercado. Paginas `/precos/` sao de conversao com precos reais. Nunca duplicar tabela de precos em artigos.

### 2.3 Hierarquia de Linkagem entre Diretorios

```
/pgrs/ ←→ /inventario-carbono/ ←→ /relatorio-sustentabilidade/
   ↓              ↓                        ↓
/setoriais/ (bidirecional — setorial cita cluster, cluster cita setorial)
   ↓
/glossario/ (linkado de todos os artigos via termos inline)
   ↓
/regulacoes/ (linkado de todos os artigos que citam leis/resolucoes)
   ↓
/blog/ (TOFU → linka para clusters; clusters → linkam para blog quando relevante)
   ↓
/ferramentas/ (linkadas como CTA mid-article em satelites relevantes)
   ↓
/casos/ (linkados como social proof em CTAs finais e paginas de preco)
```

### 2.4 Rendering Strategy (Firebase Hosting)

**IMPORTANTE**: Firebase Hosting NAO suporta ISR nativo. Estrategia adaptada:

| Pagina | Estrategia | Mecanismo |
|---|---|---|
| Artigos (pilar + satelite) | **Full SSG** | `generateStaticParams()` — rebuild on deploy |
| `/precos/` | **SSG** | Rebuild on deploy (precos mudam raramente) |
| `/glossario/` | **SSG** | `generateStaticParams()` — rebuild on deploy |
| `/regulacoes/` | **SSG** | Rebuild on deploy |
| `/setoriais/` listing | **SSG** | Rebuild on deploy |
| `/blog/` listing | **SSG** | Rebuild on deploy |
| Home | **SSG** | Rebuild on deploy |
| `/ferramentas/*` | **SSG shell + client-side** | Logica interativa no client |
| OG images | **Cloud Function** | `satori` + `sharp` via Firebase Cloud Function |
| Sitemap | **Build-time** | `app/sitemap.ts` gera no build |

**Nota sobre deploy**: Com ~51 paginas no ano 1, full SSG com rebuild on deploy (Firebase Hosting + GitHub Actions) e perfeitamente viavel. Build time < 60s. Nenhuma pagina precisa de SSR ou ISR neste volume.

**OG Images**: Usar Cloud Function com `satori` (gera SVG a partir de JSX) + `sharp` (converte para PNG). Endpoint: `https://[project].cloudfunctions.net/og?title=...&type=pgrs`. Referenciado via `<meta property="og:image">` no `generateMetadata()` de cada rota.

### 2.5 SEO Tecnico Infraestrutural

**robots.txt** (programatico via `app/robots.ts`):
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

**Core Web Vitals Targets** (corrigido — FID removido):

| Metrica | Target | Estrategia |
|---|---|---|
| LCP | < 2.5s | SSG, `next/image` com priority no hero, font preload |
| INP | < 150ms | Debounce animacoes, `content-visibility: auto`, lazy-load modais |
| CLS | < 0.1 | Dimensoes explicitas em imagens, font-display: swap com fallback metrico |
| TTFB | < 600ms | Firebase Hosting CDN global, SSG puro |
| Lighthouse Mobile | >= 90 | Auditoria mensal, bundle analysis |

---

## 3. TOPIC CLUSTERS v2.0

### 3.1 Cluster PGRS

**Pilar**: "PGRS 2025: Guia Completo do Plano de Gerenciamento de Residuos Solidos para Empresas"
**URL**: `/pgrs/`
**Keyword ancora**: "PGRS empresa como fazer"
**Volume target**: 4.500-5.000 palavras
**Schema**: Article + BreadcrumbList + HowTo
**Atualizacao**: Semestral (+ historico de atualizacoes visivel)

#### Satelites do Cluster PGRS

| # | Titulo | Keyword principal | Intent | Persona primaria | Diferencial competitivo | Volume (palavras) | Regulacoes obrigatorias |
|---|---|---|---|---|---|---|---|
| P1 | PGRS vs PGRSS vs PGRCC: Diferencas, Obrigacoes e Qual Voce Precisa | pgrs pgrss pgrcc diferenca | Informacional | Gestor PME confuso sobre qual plano precisa | Tabela comparativa unica com limiares municipais | 2.200 | Lei 12.305/2010 Art. 20, RDC 222/2018, CONAMA 307 |
| P2 | Multa por Falta de PGRS: Valores, Fiscalizacao e Como Evitar | multa falta pgrs | Informacional/Transacional | Empresario que recebeu ou teme autuacao | Valores reais de multas por estado + casos | 1.800 | Lei 12.305/2010, Lei 9.605/1998 |
| P3 | Quanto Custa um PGRS em 2025: Fatores, Faixas e Comparativo | quanto custa pgrs | Transacional/Comercial | Empresario pesquisando precos | Comparativo mercado transparente sem tabela propria | 1.800 | — |
| P4 | PGRSS para Clinicas e Consultorios: Guia Completo com RDC 222 | pgrss clinicas consultorios | Transacional | Dentista, medico, dono de clinica | Unico guia que cobre RDC 222 + CONAMA 358 + limiares por estado | 2.500 | RDC ANVISA 222/2018, CONAMA 358/2005, Lei 12.305/2010 |
| P5 | PGRSS para Veterinarias e Clinicas de Estetica | pgrss veterinaria estetica | Transacional | Veterinario, esteticista | Nicho sub-atendido, regulacao especifica | 2.200 | RDC 222/2018, CONAMA 358/2005 |
| P6 | PGRSS para Farmacias e Drogarias | pgrss farmacia | Transacional | Farmaceutico responsavel tecnico | Cobertura CRF + ANVISA especifica | 2.000 | RDC 222/2018, RDC 306/2004 (revogada, citar historico) |
| P7 | PGRCC para Construtoras: CONAMA 307 Consolidado + Guia Pratico | pgrcc construtora conama 307 | Transacional | Engenheiro civil, dono de construtora | Unico que consolida CONAMA 307 + 348 + 431 + 448 + 469 | 2.500 | CONAMA 307/2002, 348/2004, 431/2011, 448/2012, 469/2015 |
| P8 | PGRS Industria Alimenticia: ANVISA + MAPA | pgrs industria alimenticia | Transacional | Gestor de industria de alimentos | Cruzamento ANVISA + MAPA + legislacao estadual | 2.200 | Lei 12.305/2010, normas ANVISA e MAPA aplicaveis |
| P9 | PGRS Metalurgicas e Industria Quimica (Classe I) | pgrs metalurgica quimica residuos perigosos | Transacional | Gestor industrial, engenheiro de seguranca | Residuos Classe I (perigosos) — NBR 10004 | 2.200 | NBR 10004:2004, Lei 12.305/2010, CONAMA 313/2002 |
| P10 | Renovacao Anual do PGRS: Quando, Como e Quanto Custa | renovacao pgrs anual | Transacional | Cliente existente ou empresa com PGRS vencido | Checklist de renovacao + mudancas regulatorias do ano | 1.500 | Lei 12.305/2010 |
| P11 | PGRS e Alvara de Funcionamento: Exigencias por Municipio | pgrs alvara funcionamento | Informacional | Empresario abrindo empresa | Tabela de exigencias por capitais (SP, RJ, BH, POA, CWB) | 1.800 | Legislacoes municipais |
| P12 | Logistica Reversa e PGRS: Decreto 10.936/2022 | logistica reversa pgrs | Informacional | Gestor de operacoes, compliance | Integracao PGRS + logistica reversa (obrigacao legal) | 2.000 | Decreto 10.936/2022, Lei 12.305/2010 |
| P13 | Classificacao de Residuos NBR 10004: Guia Pratico | nbr 10004 classificacao residuos | Informacional | Engenheiro ambiental, tecnico | Tabela pratica de classificacao com exemplos reais | 2.000 | NBR 10004:2004, NBR 10005-10007 |
| P14 | PGRS e ISO 14001: Como Integrar | pgrs iso 14001 integracao | Informacional | Gestor de qualidade, consultor ISO | Ponte entre SGA e PGRS — sinergia documental | 1.800 | ISO 14001:2015, Lei 12.305/2010 |

**Satelites Estaduais** (5):

| # | Titulo | Keyword principal | Intent | Diferencial | Regulacoes | Mes publicacao |
|---|---|---|---|---|---|---|
| PE1 | PGRS CETESB Sao Paulo: Requisitos, Formularios e Passo a Passo | pgrs cetesb sao paulo | Transacional | Unico guia focado em CETESB com links diretos para formularios | Dec. Estadual 54.645/2009, CETESB DD 071/2003 | M3 |
| PE2 | PGRS FEAM Minas Gerais: Exigencias e Procedimentos | pgrs feam minas gerais | Transacional | Foco FEAM + COPAM | DN COPAM 217/2017 | M5 |
| PE3 | PGRS INEA Rio de Janeiro: Licenciamento e PGRS | pgrs inea rio de janeiro | Transacional | Foco INEA + SEA/RJ | DZ-1310.R-7 INEA | M6 |
| PE4 | PGRS FEPAM Rio Grande do Sul: Guia de Adequacao | pgrs fepam rs | Transacional | Foco FEPAM | Portarias FEPAM aplicaveis | M8 |
| PE5 | PGRS IAT Parana: Requisitos Especificos | pgrs iat parana | Transacional | Foco IAT (ex-IAP) | Resolucoes SEMA/PR | M10 |

### 3.2 Cluster GEE (Inventario de Carbono)

**Pilar**: "Inventario de Carbono GEE 2025: Guia Completo para Empresas Brasileiras"
**URL**: `/inventario-carbono/`
**Keyword ancora**: "inventario de carbono empresa"
**Volume target**: 4.000-5.000 palavras
**Schema**: Article + BreadcrumbList + HowTo
**Atualizacao**: Semestral

#### Satelites do Cluster GEE

| # | Titulo | Keyword principal | Intent | Persona primaria | Diferencial competitivo | Volume (palavras) | Regulacoes obrigatorias |
|---|---|---|---|---|---|---|---|
| G1 | Lei 15.042/2024 SBCE: O que Muda para Empresas Brasileiras | lei 15042 2024 sbce mercado carbono | Informacional/Urgencia | Gestor de compliance, diretor | First-mover: unico conteudo que distingue "obrigado" vs. "voluntario" com disclaimer regulamentacao pendente | 2.200 | Lei 15.042/2024 (SBCE) |
| G2 | GHG Protocol na Pratica: Como Aplicar em Empresas Brasileiras | ghg protocol empresa brasileira | Informacional | Analista ambiental, consultor | Passo a passo com Programa GHG Protocol Brasil | 2.200 | GHG Protocol Corporate Standard |
| G3 | Escopos 1, 2 e 3 de Emissoes: Guia Pratico com Exemplos | escopos 1 2 3 emissoes ghg | Informacional | Gestor ambiental iniciante | Exemplos reais por setor brasileiro | 2.500 | GHG Protocol |
| G4 | Inventario de Carbono para Fornecedores de Grandes Empresas | inventario carbono fornecedor | Transacional | PME que e fornecedora de grande empresa | Escopo 3 como driver — o que o contratante exige | 2.300 | GHG Protocol Scope 3 |
| G5 | Inventario GEE para Transportadoras e Frotas | inventario carbono transporte frota | Transacional | Dono de transportadora, gestor de frota | Fatores de emissao especificos para transporte rodoviario | 2.200 | MCTI fatores de emissao, GHG Protocol |
| G6 | Inventario de Carbono no Agronegocio e Exportacao | inventario carbono agronegocio exportacao | Transacional | Produtor rural, exportador | CBAM + Escopo 1 agricola + metano | 2.300 | GHG Protocol, CBAM (EU) |
| G7 | Inventario GEE para Tribunais e Orgaos Publicos: CNJ 594/2024 | inventario carbono tribunais cnj | Transacional | Servidor publico, TI de tribunal | Nicho ultra-especifico com demanda institucional | 2.200 | Resolucao CNJ 594/2024 |
| G8 | Inventario de Carbono para Eventos Corporativos | inventario carbono eventos | Transacional | Produtor de eventos, agencia | Nicho em crescimento (ESG + marketing) | 1.800 | GHG Protocol for Events |
| G9 | Inventario GEE para Construtoras: LEED e AQUA | inventario carbono construcao leed | Transacional | Construtora buscando certificacao verde | Integracao GEE + certificacoes verdes | 2.000 | GHG Protocol, LEED v4.1, AQUA-HQE |
| G10 | Fatores de Emissao MCTI 2025: Tabela Atualizada e Como Usar | fatores emissao mcti 2025 | Informacional | Tecnico ambiental, consultor | Tabela atualizada com fonte oficial MCTI | 2.000 | MCTI (Ministerio da Ciencia, Tecnologia e Inovacao) |
| G11 | Quanto Custa um Inventario de Carbono GEE em 2025 | quanto custa inventario carbono | Transacional | Diretor financeiro, gestor | Comparativo mercado, sem tabela propria (linka para precos) | 1.800 | — |
| G12 | Certificacao Carbono Neutro: Como Obter o Selo | certificacao carbono neutro selo | Informacional/Transacional | Diretor de marketing, gestor ESG | Passo a passo certificacao + custos reais | 2.000 | PAS 2060, normas de mercado voluntario |
| G13 | GHG Protocol vs ISO 14064: Qual Metodologia Usar | ghg protocol vs iso 14064 | Informacional | Consultor, analista ambiental | Comparativo tecnico com recomendacao por cenario | 1.800 | GHG Protocol, ISO 14064-1:2018 |
| G14 | CBAM para Exportadores Brasileiros: O que Fazer em 2025 | cbam exportadores brasileiros | Informacional/Urgencia | Exportador, diretor de comercio exterior | Urgencia real: regulacao EU em fase transitoria | 2.200 | CBAM (EU Regulation 2023/956), GHG Protocol |

### 3.3 Cluster RS (Relatorio de Sustentabilidade)

**Pilar**: "Relatorio de Sustentabilidade para PMEs 2025: Guia Completo Passo a Passo"
**URL**: `/relatorio-sustentabilidade/`
**Keyword ancora**: "relatorio de sustentabilidade empresa pequena"
**Volume target**: 4.000-4.500 palavras
**Schema**: Article + BreadcrumbList + HowTo
**Atualizacao**: Semestral

#### Satelites do Cluster RS

| # | Titulo | Keyword principal | Intent | Persona primaria | Diferencial competitivo | Volume (palavras) | Regulacoes obrigatorias |
|---|---|---|---|---|---|---|---|
| R1 | GRI Standards 2021 Simplificado para PMEs | gri standards pme simplificado | Informacional | Gestor ESG, consultor | Traducao pratica do GRI Universal para PMEs (nao so grandes empresas) | 2.500 | GRI Universal Standards 2021 |
| R2 | CVM 193/2023: Checklist de Compliance para Companhias Abertas e Efeito Cascata em PMEs | cvm 193 2023 relatorio sustentabilidade | Informacional | CFO, gestor de compliance | **CORRIGIDO**: CVM 193 obriga companhias abertas; conteudo explica efeito cascata em fornecedores PMEs | 2.200 | CVM Res. 193/2023, IFRS S1/S2 |
| R3 | IFRS S1 e S2: O que PMEs Precisam Saber Sobre Divulgacao Climatica | ifrs s1 s2 sustentabilidade | Informacional | CFO, controller | Traducao ISSB para contexto brasileiro PME | 2.200 | IFRS S1, IFRS S2, CVM 193/2023 |
| R4 | Relatorio de Sustentabilidade e Credito Bancario: BACEN 4.945 e PRSAC | relatorio sustentabilidade credito banco | Transacional | Diretor financeiro buscando credito | Conexao direta: RS → melhor score de credito | 2.000 | BACEN Res. 4.945/2021 (PRSAC), TCFD |
| R5 | Relatorio Sustentabilidade para Fornecedores de Grandes Empresas | relatorio sustentabilidade fornecedor | Transacional | PME fornecedora, gestor de contratos | Supply chain compliance — o que o contratante pede | 2.000 | GRI, SASB, requisitos contratuais |
| R6 | Relatorio de Sustentabilidade e Licitacoes Publicas | relatorio sustentabilidade licitacao | Transacional | Empresa que participa de licitacoes | Vantagem competitiva em licitacoes com criterio ESG | 1.800 | Lei 14.133/2021 (nova lei de licitacoes) |
| R7 | ESG para Empresas com Menos de 50 Funcionarios: O que Faz Sentido | esg empresa pequena 50 funcionarios | Informacional | Micro e pequeno empresario | Abordagem realista: o que vale a pena vs. overhead | 2.000 | — |
| R8 | Relatorio Sustentabilidade para Agronegocio Exportador | relatorio sustentabilidade agronegocio | Transacional | Produtor rural, cooperativa | Exigencias de importadores EU/US + EUDR | 2.200 | GRI, EUDR (EU Deforestation Regulation) |
| R9 | Relatorio Sustentabilidade para Construtoras e Incorporadoras | relatorio sustentabilidade construcao | Transacional | Construtora, incorporadora | Certificacoes + relatorio integrado | 2.000 | GRI, LEED, AQUA-HQE |
| R10 | Indicadores ESG para PMEs: Quais Medir e Como Reportar | indicadores esg pme | Informacional | Gestor que nao sabe por onde comecar | Lista curada de 15-20 indicadores realmente relevantes para PMEs | 2.200 | GRI, SASB, ODS |
| R11 | Quanto Custa um Relatorio de Sustentabilidade em 2025 | quanto custa relatorio sustentabilidade | Transacional | Diretor financeiro | Comparativo mercado, sem tabela propria | 1.800 | — |
| R12 | Relatorio de Sustentabilidade para Franqueados e Redes | relatorio sustentabilidade franquia | Transacional | Franqueador, franqueado | Modelo padronizado para redes | 1.800 | GRI |
| R13 | Matriz de Materialidade ESG: Como Fazer para PMEs | matriz materialidade esg pme | Informacional | Gestor ESG, consultor | Metodologia simplificada com template baixavel | 2.200 | GRI 3: Material Topics 2021 |
| R14 | Relatorio de Sustentabilidade para Startups: O que Investidores Exigem | relatorio sustentabilidade startup investidor | Informacional/Transacional | Fundador de startup, CFO | Foco em o que VCs e investidores realmente pedem | 2.000 | SASB, TCFD, requisitos de investidores |

### 3.4 Conteudo Cross-Cluster (`/blog/`)

Artigos TOFU e de awareness que nao pertencem a um cluster especifico, mas linkam para todos:

| # | Titulo | Keyword | Intent | Tipo | Mes planejado |
|---|---|---|---|---|---|
| B1 | O que e ESG e Por Que Sua Empresa Precisa se Preocupar em 2025 | esg empresa 2025 | TOFU/Awareness | Blog | M3 |
| B2 | 5 Multas Ambientais que PMEs Recebem Sem Saber | multa ambiental pme | TOFU/Awareness | Blog | M4 |
| B3 | Sustentabilidade Empresarial: Modismo ou Obrigacao Legal? | sustentabilidade empresarial obrigacao | TOFU/Awareness | Blog | M4 |
| B4 | Seu Contador Deveria Ter Te Avisado Sobre Isso (Compliance Ambiental) | compliance ambiental contador | TOFU/Awareness | Blog | M5 |
| B5 | Economia Circular para PMEs: Oportunidades e Primeiros Passos | economia circular pme | TOFU/Awareness | Blog | M5 |
| B6 | Selos Verdes para Empresas Brasileiras: Quais Existem e Como Obter | selos verdes empresas brasil | TOFU/Awareness | Blog | M6 |
| B7 | Plataforma de Compliance Ambiental vs. Consultoria Tradicional: Comparativo | plataforma compliance vs consultoria | MOFU/Comparativo | Blog | M3 |
| B8 | Contadores e Compliance Ambiental: Uma Parceria Necessaria | contador compliance ambiental parceria | MOFU/Parceria | Blog | M3 |
| B9 | Calendario Regulatorio Ambiental 2025: Todas as Datas que Sua Empresa Precisa Saber | calendario regulatorio ambiental 2025 | Informacional | Blog | M3 (bonus) |

---

## 4. TEMPLATE UNIVERSAL DE ARTIGO v2.0

### 4.1 Campos de Metadados (Frontmatter MDX)

```yaml
---
title: ""                    # Title tag (max 560px, front-load keyword)
h1: ""                       # H1 visivel (pode diferir do title)
metaDescription: ""          # Max 920px (~150-155 chars PT-BR)
keyword: ""                  # Keyword principal
keywordsSecondary: []        # Keywords secundarias (3-5)
intent: ""                   # informacional | transacional | comercial | navegacional
personaPrimaria: ""          # Ex: "Gestor de PME industrial, 35-50 anos, SP"
diferencialCompetitivo: ""   # O que este artigo faz que nenhum concorrente faz
clusterParent: ""            # pgrs | inventario-carbono | relatorio-sustentabilidade | blog
pageType: ""                 # pilar | satelite | tofu | comparativo | urgencia | ferramenta
regulacoes: []               # Regulacoes obrigatorias a citar
author: ""                   # Nome do autor
technicalReviewer: ""        # Nome do RT + registro profissional
publishedAt: ""              # ISO date
updatedAt: ""                # ISO date (usado em "Historico de atualizacoes")
updateHistory: []            # Array de {date, description} para pilares
wordCount: 0                 # Target
schema: []                   # Tipos de schema: Article, FAQPage, HowTo, BreadcrumbList
---
```

### 4.2 Os 14 Blocos do Template

| # | Bloco | Descricao | Regras |
|---|---|---|---|
| 1 | **Title Tag** | Keyword front-loaded nos primeiros 40 chars. Max 560px (NAO 60 chars). Sem sufixo de marca em satelites (Google appenda automaticamente). Pilares podem ter sufixo. | Medir com ferramenta de pixel (SERP Simulator ou similar) |
| 2 | **Meta Description** | Max 920px (~150-155 chars). Formula: [Problema] + [Solucao] + [CTA implicito]. Sem ponto final. | Medir por pixel, nao por caractere |
| 3 | **H1** | Proximo do Title Tag, pode ser mais longo/descritivo. Keyword obrigatoria. Unico por pagina. | Max 70 chars (flexivel — H1 nao trunca) |
| 4 | **Badge E-E-A-T** | "Revisado por [Nome do RT], [CRQ/CREA XXX] — Ultima atualizacao: [data]" | Visivel no topo, abaixo do H1 |
| 5 | **Introducao** | 150-200 palavras. Formula: Problema → Consequencia se ignorar → Promessa do artigo → Ancora para pilar (se satelite). | Keyword nos primeiros 100 chars |
| 6 | **Indice (ToC)** | Links de ancora para cada H2. Gerado automaticamente via componente MDX `<TOC />`. | Sticky em desktop, colapsavel em mobile |
| 7 | **Corpo H2s** | Min 5 H2s (satelites), 8-10 H2s (pilares). Cada H2 = subtema com intencao de busca propria. Min 1 tabela + 1 lista por artigo. | H2s formulados como perguntas quando possivel |
| 8 | **CTA Intermediario** | Apos o 3o H2. Contextual ao conteudo. Linka para **pilar do cluster** ou **ferramenta PLG** (NUNCA para precos no meio do artigo). | Componente MDX `<CTAMid href="/pgrs/" text="..." />` |
| 9 | **Dados e Referencias** | Citacoes de leis, resolucoes, normas. Links para fontes oficiais (IBAMA, CETESB, MMA, CVM, CNJ, Planalto). | Min 3 referencias por artigo. Links `rel="noopener"` |
| 10 | **Social Proof** | Depoimento de cliente, numero de documentos gerados, logos de clientes, badge CRQ/CREA. | Componente MDX `<SocialProof />`. Placeholder ate ter cases reais: usar estatistica de mercado |
| 11 | **FAQ** | **Somente em satelites**: max 5 perguntas, 2-3 linhas cada. JSON-LD FAQPage Schema. **Pilares NAO tem FAQ schema** (risco over-optimization). | Perguntas reais de clientes/GSC |
| 12 | **CTA Final** | Linka para **pagina de precos** (`/precos/` ou `/[cluster]/precos/`) OU **WhatsApp** (Lane B). Botao principal + texto de apoio. | Componente MDX `<CTAFinal type="pricing" />` ou `<CTAFinal type="whatsapp" />` |
| 13 | **Caixas de Destaque** | Avisos regulatorios, disclaimers, alertas de prazo. | Componente MDX `<InfoBox type="warning|info|deadline" />` |
| 14 | **Rodape do Artigo** | Data publicacao + ultima atualizacao + bio do autor + bio do RT. **Pilares**: adicionar "Historico de Atualizacoes" visivel. | Componente MDX `<ArticleFooter />` com dados do frontmatter |

### 4.3 Schema Markup por Tipo de Pagina

| Tipo de Pagina | Schema Types | Notas |
|---|---|---|
| Pilar (hub) | `Article` + `BreadcrumbList` + `HowTo` | SEM FAQPage (risco over-optimization) |
| Satelite | `Article` + `BreadcrumbList` + `FAQPage` (max 5) | FAQ schema apenas em satelites |
| Pagina de precos | `Service` + `BreadcrumbList` + `PriceSpecification` | Precos estruturados |
| Sobre | `ProfessionalService` + `Organization` | Credenciais E-E-A-T |
| Glossario (termo) | `DefinedTerm` + `BreadcrumbList` | Schema para definicoes |
| Ferramenta PLG | `WebApplication` + `BreadcrumbList` | Tipo de aplicacao |
| Case study | `Article` + `BreadcrumbList` + `Review` | Social proof estruturado |
| Blog TOFU | `Article` + `BreadcrumbList` | Simples |
| Relatorio setorial | `Article` + `BreadcrumbList` | + ScholarlyArticle se aplicavel |
| Regulacao | `Article` + `BreadcrumbList` + `Legislation` | Schema para legislacao |

### 4.4 Regras de CTA Corrigidas

| Posicao | Tipo de CTA | Destino | Exemplo |
|---|---|---|---|
| Mid-article (apos 3o H2) | Contextual, educacional | Pilar do cluster OU ferramenta PLG | "Saiba tudo sobre PGRS no nosso guia completo" / "Faca o autodiagnostico gratuito" |
| Final do artigo | Conversao direta | `/precos/`, `/[cluster]/precos/` ou WhatsApp | "Gere seu PGRS profissional a partir de R$990" |
| Sidebar/sticky (desktop) | Lead magnet | Download PDF/checklist (captura email) | "Baixe o checklist PGRS gratuito" |
| Exit intent (modal) | Newsletter ou lead magnet | Formulario email | "Receba alertas de mudancas regulatorias" |

**REGRA ABSOLUTA**: CTA mid-article NUNCA linka diretamente para precos. O leitor ainda esta consumindo conteudo — o CTA deve aprofundar conhecimento (pilar) ou gerar engajamento (ferramenta). CTA final e o momento da conversao.

### 4.5 Regras de Linkagem Interna (Atualizadas — 9 Regras)

| # | Regra | Detalhamento |
|---|---|---|
| R1 | Todo satelite linka para seu pilar | Anchor text com keyword do pilar, nos primeiros 200 chars da introducao |
| R2 | Pilar linka para TODOS os satelites | Atualizar pilar a cada nova publicacao de satelite |
| R3 | Cross-cluster por relevancia | Quando publico se sobrepoe (ex: construtora aparece em PGRS, GEE e RS) |
| R4 | CTA final linka para precos | Pagina `/precos/` ou `/[cluster]/precos/` |
| R5 | Relatorios setoriais linkam bidirecional | Setorial cita satelites relevantes; satelites citam setorial |
| R6 | Anchor text variado | Nunca usar mesmo texto para mesma URL em artigos diferentes |
| R7 | Min 3 links internos por artigo | 1 pilar + 1 cross-cluster + 1 precos/ferramenta |
| R8 | Glossario como link inline | Termos tecnicos linkam para `/glossario/[termo]/` na primeira ocorrencia |
| R9 | Regulacoes linkam para `/regulacoes/` | Primeira citacao de lei/resolucao linka para pagina dedicada |

---

## 5. BRIEFS DETALHADOS — MESES 1 A 3

### MES 1 — FUNDACAO (5 pecas)

**Tema**: Estabelecer os 3 pilares + capturar urgencia regulatoria + lancar primeiro PLG tool
**Objetivo**: Ter toda a arquitetura de hubs publicada antes de qualquer satelite

---

#### M1-S1: URGENCIA — Lei 15.042/2024 SBCE

**Titulo**: Lei 15.042/2024: O que o Mercado Regulado de Carbono (SBCE) Muda para Sua Empresa
**URL**: `/inventario-carbono/lei-15042-2024-sbce-mercado-carbono/`
**Keyword principal**: lei 15042 2024 sbce mercado carbono
**Keywords secundarias**: mercado regulado carbono brasil, sbce o que e, sistema brasileiro comercio emissoes, lei mercado carbono 2024
**Intencao de busca**: Informacional com urgencia regulatoria
**Persona primaria**: Diretor de compliance ou operacoes em empresa industrial media (100-500 funcionarios), que ouviu falar da lei mas nao entendeu implicacoes praticas
**Diferencial vs. concorrentes**: Unico conteudo que separa claramente "obrigado por lei" (>10.000 tCO2e/ano) vs. "deveria ter por supply chain" (PMEs fornecedoras), COM disclaimer que decreto regulamentador esta pendente
**Volume**: 2.200 palavras
**Meta-description sugerida**: Lei 15.042/2024 criou o SBCE — mercado regulado de carbono no Brasil. Entenda quem e obrigado, prazos e como PMEs sao impactadas pelo efeito cascata (max 920px)
**Estrutura H2s**:
- H2: O que e a Lei 15.042/2024 e o SBCE
- H2: Quem esta obrigado pelo SBCE (limiar de 10.000 tCO2e/ano)
- H2: Por que PMEs abaixo do limiar tambem serao impactadas (Escopo 3)
- H2: Status da regulamentacao: o que ja esta definido e o que falta
- H2: Como sua empresa pode se preparar agora (3 passos praticos)
**CTA primario (final)**: "Prepare seu inventario de carbono antes da regulamentacao → Ver precos" (linka `/inventario-carbono/precos/`)
**CTA mid-article**: "Entenda tudo sobre inventarios GEE no nosso guia completo" (linka `/inventario-carbono/`)
**Regulacoes obrigatorias**: Lei 15.042/2024, Acordo de Paris (NDC brasileira), GHG Protocol
**Disclaimer obrigatorio**: "A Lei 15.042/2024 foi sancionada em [data], porem o decreto regulamentador com detalhes de fases, prazos e limiares especificos ainda nao foi publicado. As informacoes neste artigo refletem o texto da lei e podem ser atualizadas quando a regulamentacao for emitida."
**Schema**: Article + BreadcrumbList (sem FAQ — urgencia regulatoria, atualizar frequentemente)
**Prazo publicacao**: Mes 1, Semana 1
**Justificativa da posicao**: First-mover advantage em trending regulatory content. Conteudo de urgencia deve ser publicado ANTES dos pilares por ser time-sensitive.

---

#### M1-S2: PILAR PGRS

**Titulo**: PGRS 2025: Guia Completo do Plano de Gerenciamento de Residuos Solidos para Empresas
**URL**: `/pgrs/`
**Keyword principal**: pgrs empresa como fazer
**Keywords secundarias**: plano gerenciamento residuos solidos, pgrs obrigatorio, pgrs 2025, como fazer pgrs empresa
**Intencao de busca**: Informacional com alta intencao transacional
**Persona primaria**: Gestor de PME industrial (50-200 funcionarios) que descobriu que precisa de PGRS para licenciamento/alvara e esta pesquisando como resolver
**Diferencial vs. concorrentes**: Guia mais completo do Brasil com: (1) tabela clara de quem e obrigado vs. voluntario com limiares municipais, (2) passo a passo pratico com cronograma, (3) todas as regulacoes consolidadas, (4) diferenciacao PGRS/PGRSS/PGRCC
**Volume**: 4.500-5.000 palavras
**Meta-description sugerida**: Guia completo do PGRS 2025 para empresas. Saiba quem e obrigado, como elaborar passo a passo, custos e como evitar multas de ate R$50 milhoes (max 920px)
**Estrutura H2s**:
- H2: O que e PGRS e por que sua empresa pode ser obrigada a ter
- H2: Quem precisa de PGRS: obrigatoriedade por lei vs. beneficio voluntario (tabela Art. 20 Lei 12.305)
- H2: PGRS vs PGRSS vs PGRCC: qual voce precisa (tabela comparativa)
- H2: Limiares municipais: quando sua empresa e "grande geradora" (SP, RJ, BH, POA, CWB)
- H2: Passo a passo para elaborar um PGRS profissional (8 etapas)
- H2: Documentos e credenciais necessarias (ART, RT, CRQ/CREA)
- H2: Multas e penalidades por falta de PGRS (Lei 9.605/1998)
- H2: Quanto custa um PGRS e como escolher fornecedor
- H2: Renovacao anual: o que muda e quando atualizar
- H2: Perguntas frequentes sobre PGRS (NAO usar FAQ schema — pilar)
**CTA primario (final)**: "Gere seu PGRS profissional com revisao tecnica → Ver precos" (linka `/pgrs/precos/`)
**CTA mid-article (apos H2 passo a passo)**: "Descubra se sua empresa precisa de PGRS com nosso autodiagnostico gratuito" (linka `/ferramentas/autodiagnostico/`)
**Regulacoes obrigatorias**: Lei 12.305/2010 (PNRS) Art. 20-24, Decreto 10.936/2022, Lei 9.605/1998 (crimes ambientais), NBR 10004:2004, legislacoes municipais referenciadas
**Schema**: Article + BreadcrumbList + HowTo
**Historico de atualizacoes**: Bloco visivel no rodape com log de mudancas (iniciar com "v1.0 — Publicacao original")
**Prazo publicacao**: Mes 1, Semana 2

---

#### M1-S3: PILAR Relatorio de Sustentabilidade

**Titulo**: Relatorio de Sustentabilidade para PMEs 2025: Guia Completo Passo a Passo
**URL**: `/relatorio-sustentabilidade/`
**Keyword principal**: relatorio de sustentabilidade empresa pequena
**Keywords secundarias**: relatorio sustentabilidade pme, como fazer relatorio sustentabilidade, relatorio esg pme, relatorio sustentabilidade 2025
**Intencao de busca**: Informacional com intencao transacional media
**Persona primaria**: Diretor ou socio de PME (20-100 funcionarios) que recebeu cobranca de cliente grande ou banco para apresentar relatorio ESG, e nao sabe por onde comecar
**Diferencial vs. concorrentes**: Unico guia que: (1) distingue obrigacao legal (CVM 193 — companhias abertas) de pressao de mercado (PMEs fornecedoras), (2) oferece framework simplificado para PMEs (nao e so "use GRI"), (3) conecta RS com beneficios concretos (credito, licitacoes, supply chain)
**Volume**: 4.000-4.500 palavras
**Meta-description sugerida**: Como criar um relatorio de sustentabilidade para PMEs em 2025. Framework simplificado, indicadores essenciais e como usar para credito, licitacoes e supply chain (max 920px)
**Estrutura H2s**:
- H2: O que e um relatorio de sustentabilidade e por que PMEs estao sendo cobradas
- H2: CVM 193/2023: quem e obrigado por lei vs. quem e impactado pelo efeito cascata
- H2: Frameworks disponiveis: GRI, SASB, IFRS S1/S2 — qual usar para PMEs
- H2: Framework simplificado: 15 indicadores essenciais para sua primeira versao
- H2: Passo a passo para elaborar seu relatorio (6 etapas)
- H2: Matriz de materialidade: como identificar o que importa para seu negocio
- H2: Como usar seu relatorio para conseguir credito bancario (BACEN 4.945)
- H2: Relatorio de sustentabilidade em licitacoes publicas (Lei 14.133/2021)
- H2: Quanto custa e como escolher entre plataforma e consultoria
**CTA primario (final)**: "Crie seu relatorio de sustentabilidade profissional → Ver precos" (linka `/relatorio-sustentabilidade/precos/`)
**CTA mid-article**: "Veja como funciona nossa plataforma de geracao de relatorios" (linka para demo/video ou pilar)
**Regulacoes obrigatorias**: CVM Res. 193/2023, GRI Universal Standards 2021, IFRS S1/S2, BACEN Res. 4.945/2021, Lei 14.133/2021
**Schema**: Article + BreadcrumbList + HowTo
**Historico de atualizacoes**: Bloco visivel no rodape
**Prazo publicacao**: Mes 1, Semana 3

---

#### M1-S4: PILAR Inventario de Carbono GEE

**Titulo**: Inventario de Carbono GEE 2025: Guia Completo para Empresas Brasileiras
**URL**: `/inventario-carbono/`
**Keyword principal**: inventario de carbono empresa
**Keywords secundarias**: inventario gee empresa, como fazer inventario carbono, inventario emissoes gases efeito estufa, inventario carbono 2025
**Intencao de busca**: Informacional com intencao transacional crescente
**Persona primaria**: Gestor ambiental ou de compliance em empresa media (100-500 funcionarios) que precisa reportar emissoes para cliente grande (Escopo 3) ou esta se antecipando ao SBCE
**Diferencial vs. concorrentes**: Unico guia que: (1) cobre contexto brasileiro especifico (fatores MCTI, Programa GHG Protocol Brasil), (2) distingue obrigacao legal SBCE (>10.000 tCO2e) de motivacao voluntaria, (3) inclui passo a passo com planilha de exemplo
**Volume**: 4.000-5.000 palavras
**Meta-description sugerida**: Guia completo do inventario de carbono GEE para empresas brasileiras em 2025. Escopos 1, 2 e 3, GHG Protocol, SBCE e como reduzir custos com gestao de emissoes (max 920px)
**Estrutura H2s**:
- H2: O que e um inventario de carbono e por que sua empresa deveria ter um
- H2: Obrigacao legal vs. voluntario: SBCE, supply chain e credito ESG
- H2: GHG Protocol: a metodologia padrao para inventarios no Brasil
- H2: Escopos 1, 2 e 3 explicados com exemplos brasileiros
- H2: Fatores de emissao MCTI: como usar a tabela oficial brasileira
- H2: Passo a passo para elaborar seu inventario GEE (7 etapas)
- H2: Verificacao e publicacao: Programa GHG Protocol Brasil e Registro Publico
- H2: Quanto custa e como escolher entre plataforma e consultoria
- H2: SBCE e o futuro do mercado de carbono brasileiro
**CTA primario (final)**: "Elabore seu inventario de carbono profissional → Ver precos" (linka `/inventario-carbono/precos/`)
**CTA mid-article**: "Calcule suas emissoes gratuitamente com nossa calculadora" (linka `/ferramentas/calculadora-emissoes/`)
**Regulacoes obrigatorias**: Lei 15.042/2024 (SBCE), GHG Protocol Corporate Standard, ISO 14064-1:2018, fatores MCTI
**Schema**: Article + BreadcrumbList + HowTo
**Historico de atualizacoes**: Bloco visivel no rodape
**Prazo publicacao**: Mes 1, Semana 4
**Justificativa**: Este pilar estava COMPLETAMENTE AUSENTE do plano original. Satelites GEE estavam sendo publicados sem hub page — quebra a arquitetura de topic cluster.

---

#### M1-BONUS: Auto-diagnostico de Compliance Ambiental (PLG Tool)

**Titulo da pagina**: Sua Empresa Precisa de PGRS, Inventario GEE ou Relatorio de Sustentabilidade?
**URL**: `/ferramentas/autodiagnostico/`
**Tipo**: Ferramenta interativa (quiz), NAO artigo
**Keyword principal**: compliance ambiental empresa obrigatorio
**Intencao de busca**: Informacional com alta conversao
**Persona primaria**: Empresario que nao sabe se precisa de algum documento ambiental
**Mecanica**:
- 15 perguntas (CNAE, numero funcionarios, faturamento, estado, tipo residuo, exporta?, fornecedor de grande empresa?, setor)
- Resultado: checklist personalizado com documentos obrigatorios vs. recomendados
- Captura: email + CNAE obrigatorios para ver resultado completo
- Conversao estimada: 5-15% para lead qualificado
**Schema**: WebApplication + BreadcrumbList
**Implementacao**: SSG shell + logica client-side (React state, sem backend necessario para MVP)
**Prazo**: Mes 1, Semana 4 (paralelo ao pilar GEE)
**Lead magnet vinculado**: PDF do checklist personalizado enviado por email (Brevo)

---

### MES 2 — SEGMENTACAO + URGENCIA (5 pecas)

**Tema**: Primeiros satelites de alta transacionalidade + conteudo de urgencia internacional + glossario como ativo SEO permanente
**Objetivo**: Comecar a rankear para termos transacionais de nicho + capturar trafego de urgencia CBAM

---

#### M2-S1: Quanto Custa um PGRS em 2025

**Titulo**: Quanto Custa um PGRS em 2025: Fatores, Faixas de Preco e Como Economizar
**URL**: `/pgrs/quanto-custa-pgrs/`
**Keyword principal**: quanto custa pgrs
**Keywords secundarias**: preco pgrs, valor pgrs empresa, pgrs quanto custa, custo plano gerenciamento residuos
**Intencao de busca**: Transacional/Comercial (corrigido — era "informacional" no plano original)
**Persona primaria**: Empresario pesquisando precos ativamente, comparando opcoes, proximo de contratar
**Diferencial vs. concorrentes**: Transparencia total sobre fatores que influenciam preco (porte, complexidade, estado, tipo residuo) + comparativo honesto plataforma vs. consultoria vs. freelance — SEM exibir tabela propria de precos (que fica em `/pgrs/precos/`)
**Volume**: 1.800 palavras
**Meta-description sugerida**: Descubra quanto custa um PGRS em 2025. Faixas de preco por porte, fatores que influenciam o valor e como escolher a melhor opcao para sua empresa (max 920px)
**Estrutura H2s**:
- H2: Faixas de preco do PGRS no mercado brasileiro em 2025
- H2: 6 fatores que influenciam o custo do seu PGRS
- H2: Plataforma online vs. consultoria presencial vs. freelance: comparativo de custo-beneficio
- H2: Como economizar sem comprometer a qualidade (e a legalidade)
- H2: O custo de NAO ter PGRS: multas e perdas de negocio
**CTA primario (final)**: "Veja nossos precos transparentes para PGRS → Precos PGRS" (linka `/pgrs/precos/`)
**CTA mid-article**: "Saiba quem e obrigado a ter PGRS no nosso guia completo" (linka `/pgrs/`)
**Regulacoes obrigatorias**: Lei 12.305/2010, Lei 9.605/1998 (valores de multa)
**Schema**: Article + BreadcrumbList + FAQPage (5 perguntas sobre precos)
**Prazo publicacao**: Mes 2, Semana 1

---

#### M2-S2: PGRSS para Clinicas e Consultorios

**Titulo**: PGRSS para Clinicas e Consultorios: Guia Completo com RDC 222/2018
**URL**: `/pgrs/pgrss-clinicas-consultorios/`
**Keyword principal**: pgrss clinicas consultorios
**Keywords secundarias**: pgrss clinica medica, plano gerenciamento residuos saude, pgrss consultorio odontologico, rdc 222 2018 pgrss
**Intencao de busca**: Transacional
**Persona primaria**: Dentista, medico ou dono de clinica que precisa de PGRSS para alvara/licenciamento de vigilancia sanitaria
**Diferencial vs. concorrentes**: Unico guia que cruza RDC 222/2018 (ANVISA) + CONAMA 358/2005 (tratamento/disposicao) + limiares estaduais especificos (CETESB, FEAM, INEA)
**Volume**: 2.500 palavras
**Meta-description sugerida**: Como elaborar o PGRSS da sua clinica ou consultorio. Guia completo com RDC 222/2018 ANVISA, CONAMA 358 e passo a passo para adequacao em 2025 (max 920px)
**Estrutura H2s**:
- H2: O que e PGRSS e por que clinicas e consultorios sao obrigados
- H2: RDC ANVISA 222/2018: o que muda em relacao a RDC 306
- H2: Classificacao de residuos de servicos de saude (Grupos A-E)
- H2: CONAMA 358/2005: tratamento e disposicao final de RSS
- H2: Passo a passo para elaborar o PGRSS da sua clinica
- H2: Quem pode assinar o PGRSS (RT habilitado — CRQ, CREA, CRBio, CRF, CRMV)
**CTA primario (final)**: "Gere seu PGRSS profissional com revisao por RT habilitado → Ver precos" (linka `/pgrs/precos/`)
**CTA mid-article**: "Entenda todas as diferencas entre PGRS, PGRSS e PGRCC" (linka `/pgrs/`)
**Regulacoes obrigatorias**: RDC ANVISA 222/2018, CONAMA 358/2005, Lei 12.305/2010, normas estaduais de vigilancia sanitaria
**Schema**: Article + BreadcrumbList + FAQPage (5 perguntas)
**Prazo publicacao**: Mes 2, Semana 2

---

#### M2-S3: CBAM para Exportadores Brasileiros

**Titulo**: CBAM para Exportadores Brasileiros: O que Fazer em 2025
**URL**: `/inventario-carbono/cbam-exportadores-brasileiros/`
**Keyword principal**: cbam exportadores brasileiros
**Keywords secundarias**: cbam brasil, mecanismo ajuste carbono fronteira, cbam uniao europeia exportacao, carbon border adjustment mechanism brasil
**Intencao de busca**: Informacional com urgencia real (fase transitoria em andamento)
**Persona primaria**: Diretor de comercio exterior ou compliance em empresa exportadora para UE (siderurgia, aluminio, cimento, fertilizantes, eletricidade, hidrogenio)
**Diferencial vs. concorrentes**: Foco brasileiro (nao traducao de conteudo europeu). Conexao direta: CBAM → inventario GEE → como a plataforma ajuda
**Volume**: 2.200 palavras
**Meta-description sugerida**: O CBAM da UE ja esta em fase transitoria e afeta exportadores brasileiros. Saiba quais setores, prazos e como preparar seu inventario de carbono (max 920px)
**Estrutura H2s**:
- H2: O que e o CBAM e por que exportadores brasileiros devem se preocupar
- H2: Quais setores sao afetados (lista completa)
- H2: Cronograma: fase transitoria (2023-2025) e fase definitiva (2026+)
- H2: O que exportadores brasileiros precisam reportar
- H2: Como um inventario de carbono GEE prepara sua empresa para o CBAM
**CTA primario (final)**: "Prepare seu inventario GEE para compliance CBAM → Ver precos" (linka `/inventario-carbono/precos/`)
**CTA mid-article**: "Entenda escopos 1, 2 e 3 no nosso guia completo de GEE" (linka `/inventario-carbono/`)
**Regulacoes obrigatorias**: CBAM (EU Regulation 2023/956), GHG Protocol, Lei 15.042/2024 (SBCE)
**Schema**: Article + BreadcrumbList + FAQPage (5 perguntas)
**Prazo publicacao**: Mes 2, Semana 3
**Justificativa da posicao**: Movido de Mes 8 para Mes 2 — urgencia real (fase transitoria em andamento), alta intencao transacional, primeiro conteudo CBAM em portugues com foco operacional.

---

#### M2-S4: Glossario de Sustentabilidade Empresarial

**Titulo da pagina hub**: Glossario de Sustentabilidade Empresarial: 60+ Termos Explicados
**URL hub**: `/glossario/`
**URLs individuais**: `/glossario/[termo]/` (ex: `/glossario/materialidade-esg/`, `/glossario/escopo-3/`)
**Keyword principal**: glossario sustentabilidade empresarial
**Keywords secundarias**: termos esg significado, vocabulario sustentabilidade, dicionario ambiental empresas
**Intencao de busca**: Informacional (TOFU puro)
**Persona primaria**: Qualquer profissional que encontrou um termo desconhecido e buscou no Google
**Diferencial vs. concorrentes**: Cada termo tem: definicao curta (2-3 frases) + contexto para PMEs + link para artigo relevante do site + regulacao aplicavel (quando houver)
**Volume**: 50-80 termos, ~100-200 palavras cada (pagina hub: 5.000-8.000 palavras; individuais: 200-400)
**Estrutura do hub**: Indice A-Z com links para cada termo. Termos agrupados por tema (Residuos, Carbono, ESG/RS, Regulacoes, Certificacoes).
**Termos prioritarios** (primeiros 30):
- ART, BACEN 4.945, Carbono neutro, CBAM, CETESB, Classe I/II residuos, CONAMA 307, CONAMA 358, CRQ/CREA, CVM 193, Economia circular, Escopo 1/2/3, ESG, GHG Protocol, GRI, Inventario GEE, ISO 14001, ISO 14064, LEED, Logistica reversa, Materialidade ESG, NBR 10004, PGRCC, PGRS, PGRSS, PNRS, RDC 222, Relatorio de sustentabilidade, SBCE, TCFD
**CTA**: Cada termo individual tem mini-CTA para artigo relevante do cluster. Hub tem CTA para autodiagnostico.
**Schema**: DefinedTerm (individuais) + BreadcrumbList
**Prazo publicacao**: Mes 2, Semana 4 (publicar hub + primeiros 30 termos; adicionar termos incrementalmente)
**Impacto SEO**: Low-effort, high-value. Cada termo e uma pagina indexavel que pode rankear para "[termo] significado" e gera links internos para todo o site.

---

#### M2-BONUS: Calculadora de Emissoes GEE (PLG Tool)

**Titulo da pagina**: Calculadora de Emissoes GEE: Estime seu Inventario de Carbono Gratuitamente
**URL**: `/ferramentas/calculadora-emissoes/`
**Tipo**: Ferramenta interativa (calculadora), NAO artigo
**Keyword principal**: calculadora emissoes carbono empresa
**Intencao de busca**: Transacional (ferramenta)
**Persona primaria**: Gestor ambiental que quer uma estimativa rapida antes de contratar
**Mecanica**:
- Inputs: consumo eletricidade (kWh/mes), combustivel (L/mes), viagens aereas, frota, GLP/gas natural
- Fatores de emissao MCTI embutidos
- Resultado: estimativa tCO2e/ano por escopo
- Captura: email obrigatorio para baixar PDF com resultado detalhado
- Upsell: "Para um inventario completo com verificacao, a partir de R$1.290"
**Schema**: WebApplication + BreadcrumbList
**Implementacao**: SSG shell + client-side (React, calculos no browser, sem API)
**Prazo**: Mes 2, Semana 3-4

---

### MES 3 — AUTORIDADE + COMPARATIVOS (5 pecas + bonus)

**Tema**: Primeiro conteudo estadual, comparativo competitivo, checklist regulatorio, primeiro case study, conteudo de parceria com contadores
**Objetivo**: Expandir cobertura geografica, iniciar social proof, posicionar contra consultorias tradicionais

---

#### M3-S1: PGRCC para Construtoras

**Titulo**: PGRCC para Construtoras: Guia Completo CONAMA 307 Consolidado (2002-2015)
**URL**: `/pgrs/pgrcc-construtoras-conama-307/`
**Keyword principal**: pgrcc construtora conama 307
**Keywords secundarias**: plano gerenciamento residuos construcao civil, pgrcc como fazer, conama 307 construtora, residuos construcao civil
**Intencao de busca**: Transacional
**Persona primaria**: Engenheiro civil ou dono de construtora (pequeno/medio porte) que precisa de PGRCC para licenciamento de obra
**Diferencial vs. concorrentes**: UNICO conteudo que consolida TODAS as alteracoes da CONAMA 307: original 2002 + CONAMA 348/2004 (amianto) + 431/2011 (gesso) + 448/2012 (areas de manejo) + 469/2015 (embalagens). Nenhum concorrente faz essa consolidacao.
**Volume**: 2.500 palavras
**Meta-description sugerida**: Guia completo do PGRCC para construtoras com CONAMA 307 consolidado (2002-2015). Classes de residuos, obrigacoes e como elaborar passo a passo (max 920px)
**Estrutura H2s**:
- H2: O que e PGRCC e quem e obrigado a elaborar
- H2: CONAMA 307/2002 consolidado: todas as alteracoes ate 2015
- H2: Classes de residuos da construcao civil (A, B, C, D) — o que mudou
- H2: Passo a passo para elaborar o PGRCC da sua obra
- H2: Areas de triagem, transbordo e reciclagem (CONAMA 448/2012)
- H2: Custos e como escolher fornecedor de PGRCC
**CTA primario (final)**: "Gere seu PGRCC com revisao tecnica → Ver precos" (linka `/pgrs/precos/`)
**CTA mid-article**: "Veja o guia completo de PGRS para entender todas as categorias" (linka `/pgrs/`)
**Regulacoes obrigatorias**: CONAMA 307/2002, 348/2004, 431/2011, 448/2012, 469/2015, Lei 12.305/2010
**Schema**: Article + BreadcrumbList + FAQPage (5 perguntas)
**Prazo publicacao**: Mes 3, Semana 1

---

#### M3-S2: Plataforma vs. Consultoria Tradicional

**Titulo**: Plataforma de Compliance Ambiental vs. Consultoria Tradicional: Comparativo Completo
**URL**: `/blog/plataforma-compliance-vs-consultoria-tradicional/`
**Keyword principal**: plataforma compliance ambiental vs consultoria
**Keywords secundarias**: compliance ambiental online, consultoria ambiental preco, pgrs online vs consultoria
**Intencao de busca**: Comercial/Comparativo (MOFU)
**Persona primaria**: Gestor que ja sabe que precisa de PGRS/GEE/RS e esta decidindo COMO resolver — plataforma ou consultoria
**Diferencial vs. concorrentes**: Comparativo honesto com pros e contras reais de cada abordagem. NAO e propaganda disfarçada — reconhece quando consultoria e melhor opcao (casos complexos, multinacionais, certificacao ISO).
**Volume**: 2.200 palavras
**Meta-description sugerida**: Plataforma online ou consultoria presencial para PGRS, inventario GEE e relatorio de sustentabilidade? Comparativo honesto com precos, prazos e quando usar cada opcao (max 920px)
**Estrutura H2s**:
- H2: Quando faz sentido usar uma plataforma online
- H2: Quando voce precisa de consultoria presencial
- H2: Comparativo: preco, prazo, qualidade, suporte, personalizacao
- H2: Modelo hibrido: o melhor dos dois mundos
- H2: Como avaliar se o fornecedor e confiavel (checklist)
**CTA primario (final)**: "Conheca nosso modelo hibrido → Ver precos" (linka `/precos/`)
**CTA mid-article**: "Faca nosso autodiagnostico gratuito para saber qual documento voce precisa" (linka `/ferramentas/autodiagnostico/`)
**Regulacoes obrigatorias**: N/A (conteudo comercial)
**Schema**: Article + BreadcrumbList + FAQPage (5 perguntas)
**Prazo publicacao**: Mes 3, Semana 2
**Justificativa da posicao**: Movido de Mes 7 para Mes 3. Conteudo comparativo e o tipo de maior conversao em B2B — deve existir cedo para capturar trafego de fundo de funil.

---

#### M3-S3: CVM 193/2023 Checklist

**Titulo**: CVM 193/2023: Checklist de Divulgacao de Sustentabilidade (e Efeito Cascata em PMEs)
**URL**: `/relatorio-sustentabilidade/cvm-193-2023-checklist/`
**Keyword principal**: cvm 193 2023 relatorio sustentabilidade
**Keywords secundarias**: cvm resolucao 193, divulgacao sustentabilidade cvm, ifrs s1 s2 brasil, cvm esg obrigatorio
**Intencao de busca**: Informacional (regulatorio)
**Persona primaria**: CFO ou controller de companhia aberta OU gestor de PME fornecedora de companhia aberta
**Diferencial vs. concorrentes**: **ESCOPO CORRIGIDO**: CVM 193 aplica-se a companhias abertas (CVM), NAO a PMEs diretamente. Conteudo distingue claramente: (1) obrigacao legal para companhias abertas, (2) efeito cascata para fornecedores PMEs (supply chain demands), (3) checklist pratico para ambos os cenarios.
**Volume**: 2.200 palavras
**Meta-description sugerida**: Checklist completo da CVM 193/2023 para divulgacao de sustentabilidade. Entenda quem e obrigado, prazos IFRS S1/S2 e como PMEs sao afetadas pelo efeito cascata (max 920px)
**Estrutura H2s**:
- H2: O que exige a Resolucao CVM 193/2023 (escopo: companhias abertas)
- H2: IFRS S1 e S2: os padroes de divulgacao climatica adotados
- H2: Cronograma de implementacao e prazos
- H2: O efeito cascata: por que PMEs fornecedoras serao impactadas
- H2: Checklist pratico para companhias abertas (12 itens)
- H2: Checklist para PMEs que sao fornecedoras de companhias abertas (8 itens)
**CTA primario (final)**: "Elabore seu relatorio de sustentabilidade profissional → Ver precos" (linka `/relatorio-sustentabilidade/precos/`)
**CTA mid-article**: "Veja nosso guia completo sobre relatorios de sustentabilidade para PMEs" (linka `/relatorio-sustentabilidade/`)
**Regulacoes obrigatorias**: CVM Res. 193/2023, IFRS S1 (General Requirements), IFRS S2 (Climate-related), Lei 6.404/1976, instrucoes CVM aplicaveis
**Disclaimer obrigatorio**: "A CVM 193/2023 aplica-se a companhias abertas registradas na CVM. PMEs nao sao obrigadas diretamente, mas podem ser impactadas pelas exigencias de reporte dos seus clientes de capital aberto."
**Schema**: Article + BreadcrumbList + FAQPage (5 perguntas)
**Prazo publicacao**: Mes 3, Semana 3

---

#### M3-S4: PGRS CETESB Sao Paulo

**Titulo**: PGRS CETESB Sao Paulo: Requisitos Especificos, Formularios e Passo a Passo
**URL**: `/pgrs/pgrs-cetesb-sao-paulo/`
**Keyword principal**: pgrs cetesb sao paulo
**Keywords secundarias**: pgrs sao paulo, cetesb residuos solidos, pgrs sp obrigatorio, plano residuos cetesb
**Intencao de busca**: Transacional (alta — busca local por necessidade imediata)
**Persona primaria**: Empresario ou gestor ambiental em SP que precisa de PGRS especifico para CETESB (licenciamento ambiental estadual)
**Diferencial vs. concorrentes**: Unico guia 100% focado em CETESB com: links diretos para formularios, limiares especificos de SP (>200L/dia ou >200kg/dia), referencias a Dec. Estadual 54.645/2009 e DD CETESB 071/2003
**Volume**: 2.000 palavras
**Meta-description sugerida**: Como elaborar o PGRS conforme exigencias da CETESB em Sao Paulo. Requisitos estaduais, formularios, limiares e passo a passo completo (max 920px)
**Estrutura H2s**:
- H2: Quem precisa de PGRS em Sao Paulo (limiares CETESB)
- H2: Legislacao estadual: Decreto 54.645/2009 e DD CETESB 071/2003
- H2: Formularios e documentos necessarios (com links diretos)
- H2: Passo a passo para elaborar e protocolar o PGRS na CETESB
- H2: Erros comuns que atrasam a aprovacao
**CTA primario (final)**: "Gere seu PGRS para SP com revisao tecnica → Ver precos" (linka `/pgrs/precos/`)
**CTA mid-article**: "Veja o guia completo do PGRS para entender a legislacao federal" (linka `/pgrs/`)
**Regulacoes obrigatorias**: Lei 12.305/2010, Dec. Estadual SP 54.645/2009, DD CETESB 071/2003, Politica Estadual de Residuos Solidos SP (Lei 12.300/2006)
**Schema**: Article + BreadcrumbList + FAQPage (5 perguntas)
**Prazo publicacao**: Mes 3, Semana 4
**Justificativa**: Primeiro satelite estadual. SP e o maior mercado. Conteudo estadual captura busca local de alta intencao que conteudo federal generico nao rankeia.

---

#### M3-BONUS: Calendario Regulatorio Ambiental 2025

**Titulo da pagina**: Calendario Regulatorio Ambiental 2025: Todas as Datas que Sua Empresa Precisa Saber
**URL**: `/regulacoes/calendario-regulatorio-2025/` (tambem serve como seed page para `/regulacoes/`)
**Tipo**: Pagina visual com timeline (NAO artigo longo)
**Keyword principal**: calendario regulatorio ambiental 2025
**Intencao de busca**: Informacional (ferramenta de referencia)
**Persona primaria**: Gestor de compliance que quer visao consolidada de prazos
**Formato**:
- Timeline visual mes a mes (Jan-Dez 2025)
- Cada evento: nome da regulacao + prazo + quem e afetado + link para artigo relevante
- Eventos: prazos PGRS municipais, CBAM fases, CVM 193 prazos, SBCE atualizacoes, renovacoes
- Filtro por tipo (Residuos / Carbono / ESG / Todos)
**CTA**: "Receba alertas por email quando um prazo se aproximar" (captura email)
**Schema**: Article + BreadcrumbList
**Atualizacao**: Trimestral (quando houver novas regulacoes)
**Prazo**: Mes 3, Semana 4 (publicacao junto com PGRS CETESB)
**Impacto**: Link magnet poderoso — outros sites referenciam como recurso util. Excelente para backlinks organicos.

---

## 6. CALENDARIO EDITORIAL 12 MESES v2.0

### Visao Geral

| Periodo | Pecas/mes | Total pecas | Foco |
|---|---|---|---|
| M1-M3 (Fundacao) | 5/mes | 15 + 3 bonus | Pilares, urgencia, primeiros satelites, PLG tools, glossario |
| M4-M6 (Expansao) | 4/mes | 12 | Segmentacao por setor, TOFU, estaduais, cases |
| M7-M9 (Escala) | 4/mes | 12 | Cauda longa, setoriais, refresh pilares, estaduais |
| M10-M12 (Consolidacao) | 4/mes | 12 | Profundidade tecnica, campanhas conversao, planejamento ano 2 |
| **TOTAL** | — | **51 + 3 bonus** | — |

---

### MES 1 — FUNDACAO: Pilares + Urgencia
**Tema**: Construir toda a infraestrutura de hubs antes de qualquer satelite

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Lei 15.042/2024 SBCE: O que Muda para Sua Empresa | Urgencia regulatoria | GEE | 2.200 |
| S2 | PGRS 2025: Guia Completo | **PILAR** | PGRS | 4.500 |
| S3 | Relatorio de Sustentabilidade para PMEs 2025 | **PILAR** | RS | 4.200 |
| S4 | Inventario de Carbono GEE 2025: Guia Completo | **PILAR** | GEE | 4.500 |
| Bonus | Auto-diagnostico de Compliance Ambiental | PLG Tool | Cross | — |

**Total Mes 1**: ~15.400 palavras + 1 ferramenta interativa

---

### MES 2 — SEGMENTACAO: Satelites Transacionais + Urgencia Internacional
**Tema**: Primeiros satelites de nicho com alta intencao de compra + CBAM + glossario

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Quanto Custa um PGRS em 2025 | Satelite transacional | PGRS | 1.800 |
| S2 | PGRSS para Clinicas e Consultorios (RDC 222) | Satelite transacional | PGRS | 2.500 |
| S3 | CBAM para Exportadores Brasileiros | Satelite urgencia | GEE | 2.200 |
| S4 | Glossario de Sustentabilidade (60+ termos) | Asset SEO permanente | Cross | 5.000+ |
| Bonus | Calculadora de Emissoes GEE | PLG Tool | GEE | — |

**Total Mes 2**: ~11.500+ palavras + 1 ferramenta interativa

---

### MES 3 — AUTORIDADE: Comparativos + Estadual + Regulatorio
**Tema**: Posicionamento competitivo, expansao geografica, social proof

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | PGRCC Construtoras CONAMA 307 Consolidado | Satelite transacional | PGRS | 2.500 |
| S2 | Plataforma vs. Consultoria Tradicional | Comparativo MOFU | Blog | 2.200 |
| S3 | CVM 193/2023 Checklist | Satelite regulatorio | RS | 2.200 |
| S4 | PGRS CETESB Sao Paulo | Satelite estadual | PGRS | 2.000 |
| Bonus | Calendario Regulatorio Ambiental 2025 | Pagina visual/referencia | Regulacoes | 1.500 |

**Total Mes 3**: ~10.400 palavras + 1 pagina visual

---

### MES 4 — EXPANSAO: Setores + TOFU
**Tema**: Novos segmentos industriais + primeiros artigos de awareness para topo de funil

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | PGRS Industria Alimenticia: ANVISA + MAPA | Satelite transacional | PGRS | 2.200 |
| S2 | 5 Multas Ambientais que PMEs Recebem Sem Saber | **TOFU awareness** | Blog | 1.800 |
| S3 | Inventario Carbono para Fornecedores de Grandes Empresas | Satelite transacional | GEE | 2.300 |
| S4 | Sustentabilidade Empresarial: Modismo ou Obrigacao Legal? | **TOFU awareness** | Blog | 2.000 |

**Total Mes 4**: ~8.300 palavras

---

### MES 5 — RETENCAO: Recorrencia + TOFU + Estadual
**Tema**: Renovacoes (receita recorrente), awareness, segundo estadual

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Renovacao Anual do PGRS: Quando e Como | Satelite transacional | PGRS | 1.500 |
| S2 | Seu Contador Deveria Ter Te Avisado (Compliance Ambiental) | **TOFU awareness** | Blog | 1.800 |
| S3 | PGRS FEAM Minas Gerais | Satelite estadual | PGRS | 2.000 |
| S4 | Credito BNDES/ESG + Inventario GEE | Satelite transacional | GEE | 2.000 |

**Total Mes 5**: ~7.300 palavras
**Bonus**: Primeiro case study (`/casos/`) — se houver cliente real. Se nao, substituir por "Economia Circular para PMEs" (TOFU).

---

### MES 6 — CONSOLIDACAO: Autoridade Tecnica + TOFU
**Tema**: Profundidade tecnica nos clusters + ultimos artigos TOFU + terceiro estadual

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Escopos 1, 2 e 3 de Emissoes: Guia Pratico | Satelite informacional | GEE | 2.500 |
| S2 | PGRS INEA Rio de Janeiro | Satelite estadual | PGRS | 2.000 |
| S3 | Selos Verdes para Empresas Brasileiras | **TOFU awareness** | Blog | 2.000 |
| S4 | RELATORIO SETORIAL: Emissoes na Construcao Civil 2025 (PDF + pagina) | Setorial publico | Setoriais | 3.000 |

**Total Mes 6**: ~9.500 palavras
**Bonus**: Publicar segundo case study se disponivel.

---

### MES 7 — ESCALA: Cauda Longa + Setorial
**Tema**: Termos de cauda longa por CNAE + segundo setorial

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | PGRS Metalurgicas e Industria Quimica (Classe I) | Satelite transacional | PGRS | 2.200 |
| S2 | GHG Protocol na Pratica para Empresas Brasileiras | Satelite informacional | GEE | 2.200 |
| S3 | RS para Credito Bancario: BACEN 4.945 e PRSAC | Satelite transacional | RS | 2.000 |
| S4 | RELATORIO SETORIAL: Sustentabilidade na Industria Alimenticia 2025 | Setorial publico | Setoriais | 3.000 |

**Total Mes 7**: ~9.400 palavras

---

### MES 8 — PARCERIAS: Nichos + Estadual + Contadores
**Tema**: Conteudo para parceiros contadores + quarto estadual + nichos restantes

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Contadores e Compliance Ambiental: Uma Parceria Necessaria | Blog parceria | Blog | 2.000 |
| S2 | PGRS FEPAM Rio Grande do Sul | Satelite estadual | PGRS | 2.000 |
| S3 | Indicadores ESG para PMEs: Quais Medir e Como Reportar | Satelite informacional | RS | 2.200 |
| S4 | RELATORIO SETORIAL: Sustentabilidade na Saude 2025 | Setorial publico | Setoriais | 3.000 |

**Total Mes 8**: ~9.200 palavras

---

### MES 9 — ATUALIZACAO: Refresh Pilares + Nichos
**Tema**: Atualizar pilares com novos dados + cobrir nichos restantes

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | **UPDATE**: PGRS Pilar (refresh dados, novas regulacoes, adicionar estaduais) | Refresh pilar | PGRS | +500-1.000 |
| S2 | Inventario GEE para Eventos Corporativos | Satelite transacional | GEE | 1.800 |
| S3 | ESG para Licitacoes Publicas (Lei 14.133/2021) | Satelite transacional | RS | 1.800 |
| S4 | RELATORIO SETORIAL: Sustentabilidade no Agronegocio 2025 | Setorial publico | Setoriais | 3.000 |

**Total Mes 9**: ~7.100 palavras + refresh

---

### MES 10 — PROFUNDIDADE: Tecnica Avancada + Ultimo Estadual
**Tema**: Conteudo tecnico avancado para autoridade maxima + quinto estadual

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Fatores de Emissao MCTI 2025: Tabela Atualizada | Satelite informacional | GEE | 2.000 |
| S2 | PGRS IAT Parana | Satelite estadual | PGRS | 2.000 |
| S3 | RS para Franqueados e Redes | Satelite transacional | RS | 1.800 |
| S4 | **UPDATE**: Inventario GEE Pilar (refresh SBCE, novos fatores) | Refresh pilar | GEE | +500-1.000 |

**Total Mes 10**: ~6.300 palavras + refresh

---

### MES 11 — CONVERSAO: Campanhas de Final de Ano
**Tema**: Urgencia de renovacao, bundles, conteudo de final de ano fiscal

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Urgencia: PGRS Renovacao — Nao Perca o Prazo em 2026 | Urgencia/conversao | PGRS | 1.500 |
| S2 | Inventario GEE Ano-Base 2025: Comece Agora para Fechar a Tempo | Urgencia/conversao | GEE | 1.800 |
| S3 | Bundle PGRS + GEE + RS: O Pacote Completo de Compliance para 2026 | Landing conversao | Cross | 1.200 |
| S4 | Retrospectiva Sustentabilidade PMEs 2025: O que Mudou | Blog awareness | Blog | 2.000 |

**Total Mes 11**: ~6.500 palavras
**Bonus**: Terceiro case study (trimestral).

---

### MES 12 — PLANEJAMENTO: Consolidacao + Ano 2
**Tema**: Preparacao para 2026, updates finais, anuario publico para backlinks

| Semana | Peca | Tipo | Cluster | Palavras |
|---|---|---|---|---|
| S1 | Preview: Regulacao Ambiental 2026 — O que Esperar | Blog informacional | Blog | 2.000 |
| S2 | **UPDATE**: RS Pilar (refresh CVM, IFRS, novos indicadores) | Refresh pilar | RS | +500-1.000 |
| S3 | Anuario de Emissoes PMEs 2025 (dados consolidados, PDF publico) | Setorial/link bait | Setoriais | 3.500 |
| S4 | Revisao geral: auditoria de linkagem, redirect de URLs mortas, GSC cleanup | Manutencao tecnica | — | — |

**Total Mes 12**: ~6.000 palavras + refresh + manutencao

---

### Resumo de Producao Anual

| Tipo | Quantidade | Palavras estimadas |
|---|---|---|
| Pilares (novos) | 3 | ~13.200 |
| Pilares (refresh) | 3 | ~2.000 |
| Satelites | 28 | ~58.000 |
| Blog (TOFU + comparativo + parceria) | 9 | ~18.000 |
| Relatorios setoriais | 5 | ~15.500 |
| Urgencia regulatoria | 3 | ~5.500 |
| Landing conversao | 1 | ~1.200 |
| Glossario | 1 hub + 60 termos | ~8.000 |
| Calendario regulatorio | 1 | ~1.500 |
| PLG tools | 3 | N/A (interativos) |
| Case studies | 3 | ~3.000 |
| **TOTAL** | **~60 pecas + 3 tools** | **~126.000 palavras** |

### Cronograma de PLG Tools

| Ferramenta | Mes | Cluster vinculado | Mecanismo de captura |
|---|---|---|---|
| Auto-diagnostico de Compliance | M1 | Cross (todos) | Email + CNAE para resultado |
| Calculadora de Emissoes GEE | M2 | GEE | Email para PDF detalhado |
| Gerador de PGRS Basico | M4 | PGRS | Email + dados empresa para outline; upsell para versao profissional |

### Cronograma de Case Studies

| Case | Mes | Formato | Condicao |
|---|---|---|---|
| Case #1 | M5 | `/casos/[slug]/` — 1.000 palavras | Requer 1 cliente real com autorizacao |
| Case #2 | M8 | `/casos/[slug]/` — 1.000 palavras | Idem |
| Case #3 | M11 | `/casos/[slug]/` — 1.000 palavras | Idem |

**Contingencia**: Se nao houver cliente para case study, substituir por satelite de cluster com gap (priorizar satelites P1 da lista de faltantes).

### Cadencia de Relatorios Setoriais

| Setorial | Mes | Setor | Formato |
|---|---|---|---|
| Setorial #1 | M6 | Construcao Civil | PDF + pagina web |
| Setorial #2 | M7 | Industria Alimenticia | PDF + pagina web |
| Setorial #3 | M8 | Saude | PDF + pagina web |
| Setorial #4 | M9 | Agronegocio | PDF + pagina web |
| Setorial #5 (Anuario) | M12 | Consolidado PMEs | PDF + pagina web (link bait principal) |

### Cadencia de Satelites Estaduais PGRS

| Estado | Orgao | Mes | URL |
|---|---|---|---|
| Sao Paulo | CETESB | M3 | `/pgrs/pgrs-cetesb-sao-paulo/` |
| Minas Gerais | FEAM | M5 | `/pgrs/pgrs-feam-minas-gerais/` |
| Rio de Janeiro | INEA | M6 | `/pgrs/pgrs-inea-rio-de-janeiro/` |
| Rio Grande do Sul | FEPAM | M8 | `/pgrs/pgrs-fepam-rs/` |
| Parana | IAT | M10 | `/pgrs/pgrs-iat-parana/` |

---

*Fim da Parte 1 (Secoes 1-6). Secoes 7-12 (KPIs, Monitoramento, Stack Tecnico, Backlinks, SOP, Infraestrutura de Conversao) na Parte 2.*


---

## SECAO 7: Sistema de Linkagem Interna v2.0

### 10 Regras de Linkagem

**R1 — Satelite → Pilar (obrigatorio)**
Todo satelite linka para seu pilar correspondente na introducao (primeiro ou segundo paragrafo). O anchor text deve conter a keyword principal do pilar (ex: "guia completo do PGRS"). Nunca usar "clique aqui" ou "saiba mais" como anchor.

**R2 — Pilar → Satelites (atualizar a cada publicacao)**
O pilar mantem uma secao de navegacao (tipo hub) com links para TODOS os satelites do cluster. Cada novo satelite publicado exige update imediato no pilar. Formato: titulo do satelite como anchor text, agrupado por subtema.

**R3 — Cross-cluster por relevancia (publico sobreposto)**
Satelites que atendem o mesmo segmento linkam entre si, independente do cluster. Exemplos:
- "PGRS Construtoras" ↔ "Inventario Carbono Construtoras LEED/AQUA"
- "RS Agronegocio Exportador" ↔ "Inventario Carbono Agronegocio"
- "PGRS Industria Alimenticia" ↔ "RS Indicadores ESG PMEs"

Minimo 1 cross-cluster link por artigo. Maximo 3 para evitar diluicao.

**R4 — Link para `/precos/` apenas no CTA final (corrigido)**
Reduzir links para a pagina de precos a **1 por artigo**, posicionado exclusivamente no CTA final (bloco 10 do template). O CTA de meio de artigo (bloco 7) linka para o pilar do cluster ou para um satelite relacionado de alta relevancia — nunca para `/precos/`. Justificativa: links excessivos para precos em conteudo TOFU/MOFU aumentam bounce rate e sinalizam intent mismatch.

**R5 — Relatorios setoriais como ancoras de autoridade**
Relatorios setoriais (`/setoriais/`) sao linkados nos clusters como "dados complementares" ou "leitura aprofundada". Artigos que citam dados do setor devem linkar para o relatorio correspondente. Relatorios setoriais linkam de volta para o pilar do cluster mais relevante.

**R6 — Anchor text variado (anti-over-optimization)**
Nunca usar o mesmo texto de ancora duas vezes para a mesma URL no mesmo artigo. Variar entre: keyword exata, keyword parcial, descricao contextual, titulo do artigo. Proporcao recomendada: 40% keyword exata, 30% variacao, 30% contextual.

**R7 — Minimo 3 links internos por artigo**
Composicao minima: 1 link para pilar (R1) + 1 cross-cluster (R3) + 1 link contextual (satelite do mesmo cluster, setorial, glossario, ou regulacoes). Maximo recomendado: 8 links internos por 2.000 palavras.

**R8 — Satelites estaduais linkam para pilar E versao federal (novo)**
Artigos estaduais (ex: `/pgrs/pgrs-cetesb-sao-paulo/`) devem conter:
- Link para o pilar do cluster (`/pgrs/`) no primeiro paragrafo
- Link para a versao federal generica do tema no corpo do texto (ex: artigo sobre "como fazer PGRS" em geral)
- Links cruzados para outros satelites estaduais em secao "Veja tambem por estado"

**R9 — Glossario auto-link com limite (novo)**
Termos tecnicos no corpo dos artigos linkam automaticamente para `/glossario/#termo` na primeira ocorrencia. Limite maximo: **3 glossary links por artigo** para evitar over-linking. Priorizar termos que o leitor provavelmente desconhece. Nunca linkar termos no H1, H2, ou dentro de outros links.

Termos prioritarios para auto-link: ART, PGRS, PGRSS, PGRCC, GHG Protocol, Escopo 1/2/3, SBCE, materialidade, carbono equivalente, classe I/II, CONAMA, residuo perigoso, logistica reversa, baseline, verificacao.

**R10 — Ferramentas PLG linkam para cluster e precos (novo)**
Cada pagina de ferramenta (`/ferramentas/*`) deve conter:
- Link para o pilar do cluster que a ferramenta serve (ex: calculadora GEE → `/inventario-carbono/`)
- Link para `/precos/` no CTA de conversao pos-resultado
- Links para 2-3 satelites mais relevantes como "proximos passos" apos o usuario usar a ferramenta

### Mapa de Linkagem Completo (Cross-Cluster)

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
    │ Satelites │   │ Satelites │   │ Satelites │
    │ (12+5est) │   │   (12)    │   │   (12)    │
    └─────┬─────┘   └─────┬─────┘   └─────┬─────┘
          │                │                │
          │    CROSS-CLUSTER LINKS          │
          │   (por segmento/publico)        │
          └────────────────┼────────────────┘
                           │
          ┌────────────────┼────────────────┐
          │                │                │
    ┌─────▼─────┐   ┌─────▼─────┐   ┌─────▼─────┐
    │/glossario/│   │/regulacoes│   │/setoriais/ │
    │  (hub)    │   │  (hub)    │   │  (hub)     │
    └───────────┘   └───────────┘   └────────────┘
          │                │                │
          └────────┬───────┘                │
                   │                        │
    ┌──────────────┼────────────────────────┘
    │              │
    ▼              ▼
┌─────────┐  ┌──────────┐  ┌─────────┐  ┌────────┐
│/ferramen│  │  /casos/  │  │ /precos/│  │ /sobre/│
│  tas/   │  │          │  │         │  │        │
└────┬────┘  └──────────┘  └────▲────┘  └────────┘
     │                          │
     └──────────────────────────┘
       (CTA final de ferramentas)
```

**Conexoes criticas:**
- `/glossario/` ← recebe links automaticos de todos os artigos (max 3/artigo)
- `/regulacoes/` ← recebe links de artigos que citam leis/resolucoes; linka de volta para satelites relevantes
- `/casos/` ← linkados em CTAs de social proof; linkam para `/precos/` e pilar do cluster
- `/ferramentas/*` → pilar do cluster servido + `/precos/` + satelites "proximos passos"
- `/setoriais/` ↔ satelites do mesmo segmento (bidirecional)
- `/blog/` → pilares (TOFU distribui autoridade para clusters)

---

## SECAO 8: SEO Tecnico v2.0

### 8.1 On-Page (corrigido)

#### Title Tag
- **Medicao por pixel**: maximo 560px de largura (NAO 60 caracteres — portugues com acentos e cedilhas consome mais pixels)
- **Front-load keyword**: keyword principal nos primeiros 40 caracteres
- **Sem sufixo de marca em satelites**: Google apende o nome do site automaticamente. Incluir marca apenas em Home (`/`) e `/sobre/`
- Formato satelites: `[Keyword Principal]: [Beneficio/Modificador]`
- Formato pilares: `[Keyword Principal] — Guia Completo [Ano]`
- Formato home: `[Marca] — [Proposta de Valor Curta]`

#### Meta Description
- **Maximo 920px** (~150-155 caracteres)
- Estrutura: problema + solucao + CTA implicito
- **Sem ponto final** (economiza 1 char e o truncamento fica mais natural)
- Incluir keyword principal uma vez, preferencialmente no inicio
- Exemplo: `Sua empresa precisa de PGRS mas nao sabe por onde comecar? Veja o passo a passo completo com modelos, custos e prazos para 2025`

#### H1
- Unico por pagina (sempre)
- Proximo ao title tag mas nao identico (evitar duplicacao exata)
- Conter keyword principal
- Maximo ~70 caracteres (legibilidade, nao SEO)

#### H2s
- Cada H2 contem uma variacao long-tail da keyword ou responde uma pergunta de busca
- **Minimo 5 H2s por artigo** (satelites) e **8 H2s por pilar**
- Formato recomendado: pergunta ("Como funciona X?") ou declaracao com keyword ("Custos do PGRS por segmento")
- Ordem logica: definicao → contexto → como fazer → custos → FAQ

#### URLs
- Kebab-case sem acentos: `/pgrs/pgrs-cetesb-sao-paulo/` (nao `são-paulo`)
- Maximo 4 segmentos: `/cluster/satelite/` (nunca `/cluster/sub/sub/satelite/`)
- Sem stopwords: `/pgrs/como-fazer/` nao `/pgrs/como-fazer-um-pgrs-para-empresa/`
- Sem datas na URL (conteudo evergreen)

#### Image ALT
- Descritivo + keyword contextual: `Fluxograma do processo de elaboracao do PGRS para industria alimenticia`
- Nunca: `imagem1.png`, `PGRS`, `foto do processo`
- Incluir keyword do artigo apenas quando relevante para a imagem

#### Schema Markup por Tipo de Pagina

| Tipo de Pagina | Schemas | Notas |
|---|---|---|
| Pilar (hub) | `Article` + `BreadcrumbList` + `Organization` | **SEM FAQ schema** em pilares (risco over-optimization pos-Aug 2023) |
| Satelite (artigo) | `Article` + `BreadcrumbList` + `FAQPage` | Max 5 perguntas no FAQPage |
| `/precos/` | `Service` + `Offer` + `PriceSpecification` + `BreadcrumbList` | Um `Offer` por tier (Standard/Express/Urgente) |
| `/sobre/` | `ProfessionalService` + `Organization` | Credenciais, area de atuacao, RT |
| How-to (processo) | `HowTo` + `Article` + `BreadcrumbList` | Steps com name + text + image opcional |
| `/ferramentas/*` | `SoftwareApplication` + `BreadcrumbList` | applicationCategory: "BusinessApplication" |
| Home (`/`) | `Organization` + `WebSite` com `SearchAction` | SearchAction aponta para busca interna (quando implementada) |
| `/glossario/` | `DefinedTermSet` + `BreadcrumbList` | Opcional: `DefinedTerm` por termo |
| `/regulacoes/` | `Article` + `BreadcrumbList` | dateModified critico (atualizado a cada nova regulacao) |
| `/casos/` | `Article` + `BreadcrumbList` | Incluir `about` com referencia ao servico |

#### Canonical
- Self-referencing em **todas** as paginas
- Implementar via `generateMetadata()` no Next.js 15
- URLs canonicas sempre com trailing slash consistente (definir padrao e manter)
- Paginas com parametros UTM: canonical aponta para URL limpa

#### OpenGraph
- `og:title`: igual ao title tag (sem marca)
- `og:description`: igual a meta description
- `og:image`: 1200x630px, gerado dinamicamente via Cloud Function (satori + sharp)
- `og:locale`: `pt_BR`
- `og:type`: `article` para conteudo, `website` para home/precos/sobre
- `og:site_name`: nome da marca
- `twitter:card`: `summary_large_image`

#### Robots.txt

```
User-agent: *
Allow: /

Disallow: /api/
Disallow: /admin/
Disallow: /*?utm_*
Disallow: /*?ref=*
Disallow: /_next/
Disallow: /*?draft=*
Disallow: /*?preview=*

Sitemap: https://[dominio]/sitemap.xml
```

#### X-Robots-Tag
Configurar via Next.js middleware (`middleware.ts`):
- `X-Robots-Tag: noindex` em todas as rotas `/api/*`
- `X-Robots-Tag: noindex` em URLs com `?preview=` ou `?draft=`
- Implementacao: middleware intercepta request, verifica pathname/searchParams, adiciona header

### 8.2 Core Web Vitals v2.0 (corrigido)

#### LCP < 2.5s
- Imagens em formato WebP (fallback PNG) via `next/image` com `priority` no hero
- Fontes via `next/font/google` (preload automatico, sem FOUT)
- Hero section sem JS pesado — Server Component puro
- Preconnect para dominios de terceiros (analytics, fonts)
- Imagens below-fold com `loading="lazy"`
- CSS critico inline (Tailwind ja faz via purge)

#### INP < 150ms (FID descontinuado em Marco 2024)
- **Debounce animacoes**: FAQ accordions com `requestAnimationFrame`, nao `setTimeout`
- **`content-visibility: auto`** para secoes below-fold (FAQ, footer, sidebar)
- **Lazy-load modais CTA**: carregar componente do modal apenas no click (dynamic import)
- **Sem layout shifts de hover**: `transform` e `opacity` em vez de `width`/`height` para efeitos hover
- Event handlers leves: delegar eventos quando possivel
- Evitar `JSON.parse` sincrono em interacoes do usuario

#### CLS < 0.1
- `width` e `height` explicitos em todas as tags `<Image>` (next/image faz automatico)
- Reservar espaco para embeds (iframes, videos) com aspect-ratio container
- Fontes com `font-display: swap` + tamanho de fallback ajustado (`size-adjust` via next/font)
- Nao injetar banners/CTAs acima do fold apos load

#### TTFB < 600ms
- SSG para artigos: Firebase CDN serve HTML estatico (TTFB ~50-150ms)
- Cloud Functions para rotas dinamicas: otimizar cold starts (min instances = 1 para funcoes criticas)
- Sem SSR em nenhuma pagina — tudo SSG ou SSG + rebuild
- Firebase Hosting CDN com cache headers configurados no `firebase.json`

#### Lighthouse Mobile >= 90
- Target: Performance >= 90, Accessibility >= 95, Best Practices >= 95, SEO >= 98
- CI check obrigatorio em PRs (Lighthouse CI action)
- Budget de JS: max 150KB first-load (comprimido)

### 8.3 Schema Markup Templates (JSON-LD corrigido)

#### Article (todos os artigos — pilares e satelites)

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
    "jobTitle": "{{authorTitle}}",
    "url": "https://{{domain}}/sobre/"
  },
  "publisher": {
    "@type": "Organization",
    "name": "{{brandName}}",
    "logo": {
      "@type": "ImageObject",
      "url": "https://{{domain}}/images/logo.png"
    }
  },
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "https://{{domain}}/{{path}}/"
  },
  "wordCount": {{wordCount}},
  "articleSection": "{{cluster}}"
}
```

#### FAQPage (apenas satelites — max 5 perguntas)

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "{{pergunta1}}",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "{{resposta1}}"
      }
    },
    {
      "@type": "Question",
      "name": "{{pergunta2}}",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "{{resposta2}}"
      }
    }
  ]
}
```

Nota: maximo 5 `Question` items. NAO usar em pilares. Respostas concisas (2-3 frases).

#### HowTo (artigos de processo — "como fazer")

```json
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "{{title}}",
  "description": "{{metaDescription}}",
  "totalTime": "{{estimatedTime}}",
  "estimatedCost": {
    "@type": "MonetaryAmount",
    "currency": "BRL",
    "value": "{{costEstimate}}"
  },
  "step": [
    {
      "@type": "HowToStep",
      "name": "{{stepName1}}",
      "text": "{{stepText1}}",
      "position": 1
    },
    {
      "@type": "HowToStep",
      "name": "{{stepName2}}",
      "text": "{{stepText2}}",
      "position": 2
    }
  ]
}
```

#### Service + Offer (pagina `/precos/`)

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "name": "Elaboracao de PGRS",
  "description": "Plano de Gerenciamento de Residuos Solidos para empresas conforme Lei 12.305/2010",
  "provider": {
    "@type": "Organization",
    "name": "{{brandName}}"
  },
  "areaServed": {
    "@type": "Country",
    "name": "Brasil"
  },
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "name": "Planos PGRS",
    "itemListElement": [
      {
        "@type": "Offer",
        "name": "PGRS Standard",
        "description": "Entrega em 10 dias uteis",
        "priceSpecification": {
          "@type": "PriceSpecification",
          "price": "990.00",
          "priceCurrency": "BRL"
        }
      },
      {
        "@type": "Offer",
        "name": "PGRS Express",
        "description": "Entrega em 5 dias uteis",
        "priceSpecification": {
          "@type": "PriceSpecification",
          "price": "1490.00",
          "priceCurrency": "BRL"
        }
      },
      {
        "@type": "Offer",
        "name": "PGRS Urgente",
        "description": "Entrega em 48 horas",
        "priceSpecification": {
          "@type": "PriceSpecification",
          "price": "2490.00",
          "priceCurrency": "BRL"
        }
      }
    ]
  }
}
```

Nota: replicar estrutura `Service` + `OfferCatalog` para GEE e RS na mesma pagina.

#### Organization (home + sobre)

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "{{brandName}}",
  "url": "https://{{domain}}/",
  "logo": "https://{{domain}}/images/logo.png",
  "description": "{{brandDescription}}",
  "foundingDate": "{{foundingYear}}",
  "areaServed": {
    "@type": "Country",
    "name": "Brasil"
  },
  "contactPoint": {
    "@type": "ContactPoint",
    "contactType": "customer service",
    "telephone": "{{whatsappNumber}}",
    "availableLanguage": "Portuguese"
  },
  "sameAs": [
    "https://www.linkedin.com/company/{{linkedinSlug}}/"
  ]
}
```

Na `/sobre/`, adicionar `ProfessionalService`:

```json
{
  "@context": "https://schema.org",
  "@type": "ProfessionalService",
  "name": "{{brandName}}",
  "description": "Consultoria em compliance ambiental para PMEs brasileiras",
  "priceRange": "R$490 - R$6.990",
  "knowsAbout": [
    "PGRS",
    "Inventario de Carbono GEE",
    "Relatorio de Sustentabilidade",
    "Compliance Ambiental",
    "ESG para PMEs"
  ],
  "hasCredential": [
    {
      "@type": "EducationalOccupationalCredential",
      "credentialCategory": "Professional License",
      "name": "{{credencialRT}}"
    }
  ]
}
```

#### BreadcrumbList (todas as paginas exceto home)

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "https://{{domain}}/"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "{{clusterName}}",
      "item": "https://{{domain}}/{{cluster}}/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "{{articleTitle}}",
      "item": "https://{{domain}}/{{cluster}}/{{slug}}/"
    }
  ]
}
```

#### WebSite com SearchAction (home apenas)

```json
{
  "@context": "https://schema.org",
  "@type": "WebSite",
  "name": "{{brandName}}",
  "url": "https://{{domain}}/",
  "potentialAction": {
    "@type": "SearchAction",
    "target": {
      "@type": "EntryPoint",
      "urlTemplate": "https://{{domain}}/busca/?q={search_term_string}"
    },
    "query-input": "required name=search_term_string"
  }
}
```

Nota: SearchAction so faz sentido apos implementar Pagefind (Mes 4+). Incluir no schema apenas quando busca interna estiver funcional.

### 8.4 Content Freshness Strategy (novo)

#### Tiers de Atualizacao

| Tier | Criterio | Acoes | Frequencia |
|---|---|---|---|
| **Major Update** | >15% do conteudo reescrito, nova secao adicionada, dados atualizados significativamente | Atualizar `dateModified`, adicionar "Historico de atualizacoes" visivel, re-submeter ao GSC, postar no LinkedIn | Quando necessario |
| **Minor Update** | Links corrigidos, typos, formatacao, clarificacao de frase | Atualizar `dateModified` apenas (sem changelog visivel) | Conforme necessidade |
| **Regulatory Trigger** | Nova lei, resolucao, decreto, ou alteracao que afeta o topico | Atualizar dentro de **72 horas**, major update, destaque visual "Atualizado em DD/MM/AAAA", alert box no topo | Sob demanda |
| **Scheduled Review** | Revisao planejada no calendario | Verificar dados, links, CTAs, posicao no GSC | Pilares: semestral. Satelites: anual |

#### Secao "Historico de Atualizacoes" (obrigatoria em pilares)

Incluir no final de todos os pilares, antes do FAQ:

```markdown
## Historico de Atualizacoes

| Data | Tipo | Descricao |
|---|---|---|
| DD/MM/AAAA | Publicacao original | Versao inicial publicada |
| DD/MM/AAAA | Atualizacao regulatoria | Incluida referencia a [nova lei/resolucao] |
| DD/MM/AAAA | Revisao semestral | Dados de custos atualizados, novos satelites linkados |
```

#### Sinais de Freshness para Google
- `datePublished` e `dateModified` no frontmatter MDX de todo artigo
- `lastmod` no sitemap.xml gerado automaticamente do frontmatter
- Artigos com `dateModified` > 12 meses sem update: flag no CI para revisao
- Artigos regulatorios: monitorar DOU (Diario Oficial da Uniao) semanalmente para triggers

#### Calendario de Revisoes

| Conteudo | Frequencia de Revisao | Responsavel |
|---|---|---|
| Pilares (3) | Semestral (Mes 6 e 12) | Fundador + RT |
| Satelites regulatorios | A cada nova regulacao (72h) | Fundador |
| Satelites evergreen | Anual | Fundador |
| `/precos/` | Mensal (ajustes de mercado) | Fundador |
| `/regulacoes/` | Trimestral + triggers | Fundador + RT |
| `/glossario/` | Trimestral (novos termos) | Fundador |

---

## SECAO 9: Funil de Conversao v2.0

### 9.1 Lead Magnets (1 por cluster)

| Cluster | Lead Magnet | Formato | Conteudo | Objetivo |
|---|---|---|---|---|
| **PGRS** | "Checklist: Sua empresa precisa de PGRS?" | PDF (3-5 paginas) | 15 perguntas sim/nao baseadas em Lei 12.305 Art. 20, limiares municipais (SP/RJ/BH/PR/RS), classificacao CNAE. Resultado: "obrigado", "recomendado", ou "nao aplicavel" com proximos passos | Qualificar leads por obrigatoriedade; capturar email + CNAE |
| **GEE** | "Planilha: Calculadora simplificada de emissoes CO2" | Google Sheets (template copiavel) | Inputs: consumo energia (kWh), combustivel (L), viagens (km). Output: tCO2e estimado por escopo. Fatores de emissao MCTI embutidos. Disclaimer de simplificacao | Demonstrar valor do inventario completo; capturar email para acesso |
| **RS** | "Template: Modelo de Relatorio GRI Simplificado" | DOCX (10-15 paginas) | Estrutura basica GRI Standards 2021 adaptada para PMEs. Secoes pre-montadas com instrucoes. Indicadores obrigatorios vs. opcionais marcados | Reduzir intimidacao do relatorio; mostrar que a versao profissional e muito melhor |

**Regras de lead magnets:**
- Gate leve: nome + email + setor/CNAE (3 campos)
- Entrega imediata (download link na thank-you page + email de confirmacao)
- Follow-up automatico inicia nurture sequence (ver 9.3)
- Design profissional (template Canva ou Figma) com marca e contato

### 9.2 Conversion Paths (3 caminhos por intencao)

#### Path 1 — Cold (visitante informacional)
```
Artigo TOFU/MOFU → CTA lead magnet no meio do artigo
  → Download (captura email + CNAE)
    → Email nurture sequence (5-7 emails, 14-21 dias)
      → Email final: "Agende uma consulta gratuita de 15 min"
        → Calendly/WhatsApp → Diagnostico → Proposta
```
- **Timeline**: 14-30 dias do primeiro contato ate qualificacao
- **Taxa esperada**: 1-3% artigo→lead magnet, 5-10% lead magnet→consulta

#### Path 2 — Warm (visitante com intencao comercial)
```
Pagina de precos OU artigo "quanto custa" → CTA "Fale com especialista"
  → WhatsApp pre-preenchido com servico + tier
    → Conversa diagnostica (5-10 min)
      → Proposta personalizada em 24h
        → Follow-up WhatsApp em 48h se sem resposta
```
- **Timeline**: 1-7 dias
- **Taxa esperada**: 3-8% pricing→WhatsApp, 20-40% WhatsApp→proposta

#### Path 3 — Hot (visitante com urgencia)
```
Artigo urgencia/multa/prazo → CTA "Regularize em 5 dias uteis"
  → WhatsApp direto (mensagem pre-preenchida com urgencia)
    → Diagnostico por telefone (mesmo dia)
      → Proposta Express/Urgente em 2h
        → Fechamento em 24-48h
```
- **Timeline**: 0-48h
- **Taxa esperada**: 5-15% artigo urgencia→WhatsApp, 30-50% WhatsApp→fechamento

### 9.3 Email Nurture Sequences (3 sequencias)

#### Sequencia PGRS (7 emails, 21 dias)

| # | Dia | Assunto | Conteudo | CTA |
|---|---|---|---|---|
| 1 | 0 | Seu checklist PGRS esta aqui | Entrega do lead magnet + breve intro da marca | Download checklist |
| 2 | 3 | Voce sabia que a multa por falta de PGRS chega a R$50 milhoes? | Dados sobre fiscalizacao + Lei 12.305 | Ler artigo sobre multas |
| 3 | 7 | Como saber qual profissional assina seu PGRS | Explicacao CRQ/CREA/CRBio + importancia do RT | Ler artigo credenciais |
| 4 | 10 | PGRS na pratica: o que orgaos ambientais realmente exigem | Checklist simplificado do que contem um PGRS valido | Ler pilar PGRS |
| 5 | 14 | Quanto custa um PGRS (e quanto custa NAO ter) | Comparativo custo vs. multa/embargo + tabela de precos | Ver precos |
| 6 | 18 | Como [empresa do setor X] regularizou em 10 dias | Case study ou exemplo hipotetico (se ainda nao tiver cases reais) | Agendar consulta |
| 7 | 21 | Ultima chance: diagnostico gratuito de compliance | Oferta de consulta de 15 min sem compromisso | WhatsApp/Calendly |

#### Sequencia GEE (5 emails, 14 dias)

| # | Dia | Assunto | Conteudo | CTA |
|---|---|---|---|---|
| 1 | 0 | Sua planilha de emissoes esta pronta | Entrega do lead magnet + contexto SBCE | Acessar planilha |
| 2 | 3 | Lei 15.042/2024: o que muda para sua empresa | Resumo SBCE + disclaimer regulamentacao pendente | Ler artigo SBCE |
| 3 | 7 | Escopos 1, 2 e 3: por que seu cliente ja esta perguntando | Supply chain pressure + exigencias de grandes empresas | Ler artigo escopos |
| 4 | 10 | Da planilha ao inventario profissional: qual a diferenca | Limitacoes da planilha vs. inventario GHG Protocol completo | Ver precos GEE |
| 5 | 14 | Seu inventario de carbono em 10 dias: vamos conversar? | Oferta de diagnostico gratuito | WhatsApp/Calendly |

#### Sequencia RS (5 emails, 14 dias)

| # | Dia | Assunto | Conteudo | CTA |
|---|---|---|---|---|
| 1 | 0 | Seu template GRI simplificado esta aqui | Entrega do lead magnet + contexto CVM/ISSB | Download template |
| 2 | 3 | CVM 193/2023: nao obriga PMEs, mas o efeito cascata ja chegou | Framing correto: supply chain, credito bancario, licitacoes | Ler artigo CVM |
| 3 | 7 | O relatorio que abre portas: credito, licitacoes e grandes clientes | Beneficios tangaiveis de ter RS mesmo sem obrigacao | Ler pilar RS |
| 4 | 10 | Do template ao relatorio profissional: o que muda | Limitacoes do template vs. relatorio completo | Ver precos RS |
| 5 | 14 | Vamos montar seu relatorio juntos? 15 min para comecar | Oferta de diagnostico | WhatsApp/Calendly |

#### Digest Regulatorio Mensal
- Enviado para **todos** os subscribers (todas as sequencias)
- Conteudo: 3-5 novidades regulatorias do mes + link para artigos relevantes
- Formato: newsletter curta (300-500 palavras)
- Objetivo: manter engajamento pos-nurture, reativar leads frios

#### Ferramenta
- **Brevo** (free tier): 300 emails/dia, automacao de workflows, templates HTML
- Segmentacao por: cluster de interesse (PGRS/GEE/RS), CNAE, lead score, estagio do funil

### 9.4 Social Proof Strategy

#### Mes 1 — Credibilidade Institucional
- Badges visiveis no header/footer: registro CRQ/CREA do RT, metodologia GHG Protocol, referencias a normas (ABNT, ISO)
- Secao "Fundamentacao Legal" nos artigos com links para legislacao original
- Foto e bio do RT com credenciais na pagina `/sobre/`
- Selo "Empresa registrada" (quando aplicavel)

#### Mes 2-3 — Primeiros Indicadores
- Contador de documentos elaborados (mesmo que comece em numeros pequenos: "10+ empresas atendidas")
- Primeiros depoimentos de clientes (solicitar ativamente apos entrega)
- Logo bar dos primeiros clientes (com permissao)
- Ratings Google Business Profile (solicitar avaliacao apos entrega)

#### Mes 6+ — Case Studies
- 1 case study por trimestre em `/casos/`
- Estrutura: desafio → solucao → resultados (com numeros reais)
- Formato: pagina web + PDF downloadavel
- Segmentar por cluster: 1 case PGRS, 1 GEE, 1 RS (ao longo de 12 meses)

#### Proof Boxes em Artigos
Componente MDX reutilizavel `<ProofBox>` para inserir em artigos:

```
┌──────────────────────────────────────────┐
│  📊 Dado Real                             │
│  "Em 2024, o IBAMA aplicou R$X bilhoes   │
│   em multas ambientais, XX% para PMEs"   │
│  — Fonte: IBAMA, Relatorio Anual 2024    │
└──────────────────────────────────────────┘
```

Usar em todo artigo que cita dados: referencia obrigatoria a fonte oficial (IBAMA, MMA, CETESB, CVM, BACEN).

### 9.5 WhatsApp Integration

#### Botao Flutuante
- Presente em **todas** as paginas (exceto `/admin/`)
- Posicao: canto inferior direito, acima do fold em mobile
- Design: icone WhatsApp padrao (verde) + badge com texto "Fale conosco"
- Comportamento: aparece apos 5 segundos ou 30% scroll (o que acontecer primeiro)
- Desaparece durante leitura ativa (scroll down), reaparece no scroll up

#### Mensagens Pre-Preenchidas por Produto

| Origem | Mensagem Pre-Preenchida |
|---|---|
| `/pgrs/` e satelites | `Ola! Vim do site e tenho duvidas sobre PGRS para minha empresa.` |
| `/inventario-carbono/` e satelites | `Ola! Preciso de informacoes sobre inventario de carbono GEE.` |
| `/relatorio-sustentabilidade/` e satelites | `Ola! Quero saber mais sobre relatorio de sustentabilidade.` |
| `/precos/` | `Ola! Vi os precos no site e gostaria de um orcamento personalizado.` |
| `/ferramentas/*` (pos-resultado) | `Ola! Usei a [ferramenta] no site e quero saber sobre o servico completo.` |
| Artigos de urgencia | `Ola! Preciso regularizar minha empresa com urgencia. Podem me ajudar?` |
| CTA "Regularize em 5 dias" | `URGENTE: Preciso de [servico] com prazo Express. Qual a disponibilidade?` |

#### Mobile
- Click-to-call no header (numero de telefone visivel, `tel:` link)
- WhatsApp button maior em mobile (48x48px minimo para touch target)
- Sticky CTA bar no bottom em artigos longos (mobile only)

### 9.6 Formularios

#### Formulario de Intake (principal)
Maximo **5 campos**:

| Campo | Tipo | Obrigatorio | Validacao |
|---|---|---|---|
| Nome completo | Text | Sim | Min 3 chars |
| Email corporativo | Email | Sim | Regex email |
| CNAE ou Setor | Select (dropdown) | Sim | Lista de 15-20 setores mais comuns |
| Servico de interesse | Select | Sim | PGRS / GEE / RS / Bundle / Nao sei |
| Nivel de urgencia | Radio | Nao | Normal (10 dias) / Rapido (5 dias) / Urgente (48h) |

**Nao incluir**: telefone (sera coletado no WhatsApp), CNPJ (intimidador), tamanho empresa (irrelevante neste estagio).

#### Thank-You Page
Apos envio do formulario, redirecionar para pagina com:

1. **Expectativa**: "Entraremos em contato em ate 24h por email ou WhatsApp"
2. **Social proof**: "Junte-se a X+ empresas que ja regularizaram" + depoimento rapido
3. **Bundle upsell**: "Empresas que contratam PGRS tambem precisam de: [Inventario GEE] [Relatorio RS] — Economize 25% no bundle"
4. **Conteudo**: link para o artigo pilar mais relevante ao servico escolhido
5. **WhatsApp alternativo**: "Prefere resolver agora? Fale pelo WhatsApp" (para leads impacientes)

#### Armazenamento
- Submissions salvas em Firebase Firestore (collection `leads`)
- Cloud Function trigada por novo documento: envia notificacao para WhatsApp do fundador via webhook
- Campos adicionais automaticos: timestamp, UTM source/medium/campaign, pagina de origem, user agent

### 9.7 A/B Testing Framework

#### Ferramenta
- **PostHog** (free tier): 1M eventos/mes, feature flags, session replays
- Implementacao via `@posthog/next` (SDK oficial para Next.js)
- Eventos trackeados: page_view, cta_click, lead_magnet_download, form_submit, whatsapp_click, pricing_view

#### Prioridade de Testes (ordem sequencial)

| Prioridade | Teste | Hipotese | Metrica |
|---|---|---|---|
| 1 | CTA copy | "Solicitar orcamento" vs. "Ver meu diagnostico gratuito" vs. "Regularize sua empresa" | CTR no botao |
| 2 | CTA placement | CTA apos H2 #3 vs. CTA flutuante lateral vs. CTA sticky bottom (mobile) | Clicks por sessao |
| 3 | Lead magnet offer | Checklist PDF vs. Quiz interativo vs. Planilha editavel | Taxa de download |
| 4 | Pricing layout | Cards horizontais vs. tabela comparativa vs. slider interativo | Tempo na pagina + click no tier |
| 5 | Social proof | Com depoimento vs. sem vs. com contador numerico | Conversao form/WhatsApp |
| 6 | Form length | 5 campos vs. 3 campos (nome, email, servico) | Taxa de submissao |

#### Regras de Teste
- **Minimo 200 conversoes por variante** antes de declarar vencedor (significancia estatistica)
- Rodar apenas **1 teste por vez** por pagina (evitar interacao de variaveis)
- Duracao minima: 14 dias (capturar dia-da-semana e variacao natural)
- Documentar todo teste: hipotese, variantes, resultado, aprendizado
- Testes negativos (piora >5%): encerrar imediatamente

### 9.8 Lead Scoring

#### Modelo de Pontuacao

| Acao | Pontos | Categoria |
|---|---|---|
| Visitou artigo TOFU | +5 | Engajamento |
| Visitou artigo MOFU/BOFU | +10 | Engajamento |
| Visitou pagina de precos | +20 | Intencao |
| Visitou precos 2x+ | +15 (adicional) | Intencao alta |
| Leu 3+ artigos em 7 dias | +15 | Engajamento |
| Baixou lead magnet | +15 | Qualificacao |
| Usou ferramenta/calculadora | +20 | Qualificacao |
| Abriu email nurture | +5 | Engajamento |
| Clicou link no email | +10 | Engajamento |
| Clicou "Contratar" ou "Solicitar" | +25 | Intencao alta |
| Visitou artigo de urgencia/multa | +15 | Urgencia |
| Enviou formulario | +30 | Conversao |
| Inatividade >30 dias | -20 | Decay |

#### Faixas e Acoes

| Faixa | Score | Status | Acao Automatica |
|---|---|---|---|
| **Cold** | 1-30 | Informacional | Email nurture sequence. Nenhum contato direto. |
| **Warm** | 31-70 | Consideracao | Email personalizado (nao automatico) + mensagem WhatsApp em 24h. Priorizar leads com CNAE de alto valor. |
| **Hot** | 71-100 | Decisao | WhatsApp em ate 2h. Ligacao telefonica no mesmo dia. Proposta personalizada. Oferecer diagnostico gratuito. |

#### Implementacao
- Tracking via PostHog (eventos) + Brevo (email engagement)
- Score calculado em Cloud Function schedulada (diaria)
- Leads hot: notificacao instantanea via WhatsApp webhook para fundador
- Dashboard simples em Firestore: lista de leads ordenada por score com historico de acoes

---

## SECAO 10: Stack Tecnico v2.0

### 10.1 Ferramentas SEO/Marketing (R$0-150/mes)

| Ferramenta | Funcao | Custo | Tier |
|---|---|---|---|
| Google Search Console | Indexacao, posicoes, CTR, erros | R$0 | Essencial |
| Google Analytics 4 | Trafego, conversoes, comportamento | R$0 | Essencial |
| Google Keyword Planner | Pesquisa de keywords, volume | R$0 | Essencial |
| Ahrefs Webmaster Tools | Backlinks, saude do site | R$0 | Essencial |
| Screaming Frog (free) | Auditoria tecnica (500 URLs) | R$0 | Essencial |
| PageSpeed Insights | Core Web Vitals, Lighthouse | R$0 | Essencial |
| Schema Markup Generator (Merkle) | Validacao JSON-LD | R$0 | Essencial |
| Hemingway / LanguageTool | Revisao de texto | R$0 | Essencial |
| Canva (free) | Design lead magnets, social | R$0 | Essencial |
| **Brevo** (free tier) | Email marketing, automacao | R$0 (300 emails/dia) | Essencial |
| **PostHog** (free tier) | A/B testing, analytics, feature flags | R$0 (1M eventos/mes) | Essencial |
| **WhatsApp Business** | Canal de conversao direto | R$0 | Essencial |
| Google Business Profile | Presenca local, reviews | R$0 | Essencial |
| Google Ads (opcional) | Campanhas high-intent | R$500-1.000/mes | Mes 1+ |

**Custo total mensal**: R$0 (sem Ads) a R$1.000 (com Ads)

### 10.2 Stack de Desenvolvimento

| Componente | Tecnologia | Justificativa |
|---|---|---|
| Framework | **Next.js 15 (App Router)** | Server Components, `generateMetadata`, route groups, otimizacoes built-in |
| Content | **MDX no repo** (`@next/mdx`) | 4-5 artigos/mes, template rigido, Git versioning, R$0, sem vendor lock-in |
| Styling | **Tailwind CSS** | Utility-first, purge automatico, iteracao rapida, CSS minimo |
| Hosting | **Firebase Hosting** | CDN global (151+ PoPs), free tier generoso (10GB storage, 360MB/dia transfer), integra com Cloud Functions |
| Dynamic routes | **Cloud Functions for Firebase** | OG image generation, search API, form handling, lead notifications |
| OG Images | **satori + sharp** (via Cloud Function) | Geracao dinamica sem dependencia Vercel. satori renderiza JSX→SVG, sharp converte→PNG |
| SEO Metadata | **Built-in Metadata API** (`generateMetadata`) | NAO usar next-seo (redundante no App Router, padrao Pages Router) |
| JSON-LD | **Custom `<JsonLd>` Server Component** | Zero bundle size (server-only), tipado com TypeScript, auto-gerado do frontmatter MDX |
| Sitemap | **next-sitemap** | Geracao pos-build com `lastmod` do frontmatter. Suporta sitemap index para >50K URLs |
| Search | **Pagefind** (Mes 4+) | Indice estatico gerado no build, stemming portugues, zero custo runtime, ~50KB client |
| Analytics | **@next/third-parties** (GA4) | Carregamento diferido, sem GTM necessario, script otimizado |
| Email | **Brevo** (free tier) | 300 emails/dia, workflows de automacao, API REST, templates HTML |
| A/B Testing | **PostHog** (free tier) | 1M eventos/mes, feature flags server-side, session replay |
| Forms | **Firebase Firestore** | Submissao serverless via Cloud Function, realtime listeners, free tier: 50K reads/dia |
| Monitoring | **Firebase Performance Monitoring** | Web Vitals automaticos, custom traces, integrado ao console |

### 10.3 Arquitetura Especifica Firebase

#### Limitacao ISR e Solucoes

Firebase Hosting serve arquivos estaticos — NAO suporta ISR (Incremental Static Regeneration) nativo do Next.js. Estrategia:

**Paginas de artigo (pilares + satelites): SSG puro**
- `next build` gera HTML estatico para todas as rotas de conteudo
- Firebase CDN serve diretamente (TTFB ~50-150ms)
- Rebuild completo via `firebase deploy` quando conteudo muda
- Com 80-100 paginas, build completo leva ~2-3 minutos — aceitavel

**Paginas que "precisariam" de ISR (home, /precos/, listings): SSG + rebuild programado**
- Gerar estaticamente no build (dados hardcoded ou lidos do frontmatter)
- Para atualizacoes frequentes: GitHub Actions webhook trigado por:
  - Push no branch `main` (deploy automatico)
  - Cron schedule (ex: rebuild diario as 6h para atualizar datas/contadores)
  - Cloud Function que chama GitHub Actions API quando um formulario altera dados exibidos

```
Fluxo de rebuild:
Content update (push MDX) → GitHub Actions → next build → firebase deploy → CDN atualizado
                                                                              (~3-5 min total)
```

**Alternativa: Firebase App Hosting (GA desde 2025)**
- Suporta Next.js SSR nativo via Cloud Run
- Vantagem: ISR real, sem workarounds
- Desvantagem: cold starts do Cloud Run (~1-3s), custo por request (nao free tier), complexidade adicional
- **Recomendacao**: comecar com SSG puro no Firebase Hosting. Migrar para App Hosting apenas se o volume de conteudo ultrapassar 200+ paginas e rebuilds ficarem lentos (>10 min)

#### Cloud Function: OG Image Generator

```
Request flow:
GET /og/{slug}.png → Cloud Function
  1. Le frontmatter do artigo via slug (armazenado em Firestore ou JSON estatico no deploy)
  2. Monta JSX template com: titulo, cluster badge, logo, gradiente de fundo
  3. satori renderiza JSX → SVG (server-side, sem browser)
  4. sharp converte SVG → PNG 1200x630
  5. Salva em Cloud Storage (cache)
  6. Retorna PNG com Cache-Control: public, max-age=604800 (7 dias)
  7. Requests subsequentes servidas do Cloud Storage cache
```

Config no `firebase.json`:
```json
{
  "hosting": {
    "rewrites": [
      {
        "source": "/og/**",
        "function": "ogImage"
      }
    ]
  }
}
```

#### Cloud Function: Form Handler

```
Request flow:
POST /api/form → Cloud Function
  1. Valida campos (nome, email, CNAE, servico, urgencia)
  2. Sanitiza inputs (XSS, injection)
  3. Salva em Firestore collection 'leads' com:
     - campos do formulario
     - timestamp
     - UTM params (da query string ou referrer)
     - pagina de origem
     - user agent
  4. Calcula lead score inicial (baseado em servico + urgencia)
  5. Envia notificacao para WhatsApp do fundador via webhook (Twilio ou Z-API)
  6. Se urgencia == "urgente": envia tambem SMS
  7. Retorna { success: true, redirect: "/obrigado/" }
```

#### Cloud Function: Lead Score Calculator (scheduled)

```
Schedule: a cada 24h (Firebase Scheduled Functions)
  1. Le todos os leads com last_activity > 24h atras
  2. Busca eventos PostHog via API (page views, clicks)
  3. Busca engagement Brevo via API (opens, clicks)
  4. Calcula score atualizado (ver modelo 9.8)
  5. Atualiza Firestore document do lead
  6. Se lead mudou de faixa (cold→warm, warm→hot): trigger notificacao
```

### 10.4 Deployment Pipeline

#### GitHub Actions: Deploy Principal

```yaml
# .github/workflows/deploy.yml
Trigger: push to main
Steps:
  1. Checkout repo
  2. Setup Node 20
  3. npm ci
  4. Validate MDX content (frontmatter completeness, word count, link count)
  5. next build (output: out/ or .next/)
  6. firebase deploy --only hosting
  7. firebase deploy --only functions (se functions/ mudou)
  8. Notify (Slack/Discord webhook opcional)
```

#### Lighthouse CI em PRs

```yaml
# .github/workflows/lighthouse-ci.yml
Trigger: pull_request
Steps:
  1. Build preview
  2. Serve localmente (ou deploy preview channel Firebase)
  3. Run Lighthouse CI contra 5 URLs representativas:
     - Home
     - 1 pilar
     - 1 satelite
     - /precos/
     - 1 ferramenta
  4. Assert: Performance >= 90, A11y >= 95, SEO >= 98
  5. Post resultado como comment no PR
```

#### Validacao de Conteudo MDX

```yaml
# .github/workflows/content-quality.yml
Trigger: push (paths: content/**)
Checks:
  - Frontmatter completo: title, description, date, author, cluster, keywords (all required)
  - Word count minimo: pilar >= 3500, satelite >= 1800, urgencia >= 1500
  - Link count minimo: >= 3 internos
  - H2 count minimo: pilar >= 8, satelite >= 5
  - Nenhum link quebrado interno (resolvivel no build)
  - dateModified >= datePublished
  - slug sem acentos, kebab-case
  - Images com alt text
```

#### Broken Link Checker (cron semanal)

```yaml
# .github/workflows/broken-links.yml
Trigger: schedule (cron: '0 8 * * 1') # segunda 8h UTC
Steps:
  1. Crawl site publicado com lychee ou linkchecker
  2. Reportar links quebrados (internos e externos)
  3. Criar issue automatica no GitHub se encontrar quebras
```

### 10.5 Estrutura do Projeto

```
paloma/
├── .github/
│   └── workflows/
│       ├── deploy.yml                    # Push to main → build → firebase deploy
│       ├── lighthouse-ci.yml             # Lighthouse em PRs
│       ├── content-quality.yml           # Validacao MDX em pushes
│       └── broken-links.yml              # Cron semanal link checker
│
├── app/
│   ├── layout.tsx                        # Root: fonts (next/font), analytics, nav, footer
│   ├── page.tsx                          # Home (SSG)
│   ├── sitemap.ts                        # Programatico (next-sitemap)
│   ├── robots.ts                         # Programatico
│   ├── not-found.tsx                     # 404 custom
│   │
│   ├── pgrs/
│   │   ├── page.tsx                      # Pilar PGRS (SSG)
│   │   └── [slug]/
│   │       └── page.tsx                  # Satelite PGRS (SSG)
│   │
│   ├── inventario-carbono/
│   │   ├── page.tsx                      # Pilar GEE (SSG)
│   │   └── [slug]/
│   │       └── page.tsx                  # Satelite GEE (SSG)
│   │
│   ├── relatorio-sustentabilidade/
│   │   ├── page.tsx                      # Pilar RS (SSG)
│   │   └── [slug]/
│   │       └── page.tsx                  # Satelite RS (SSG)
│   │
│   ├── setoriais/
│   │   ├── page.tsx                      # Listing setoriais (SSG)
│   │   └── [slug]/
│   │       └── page.tsx                  # Relatorio individual (SSG)
│   │
│   ├── blog/
│   │   ├── page.tsx                      # Listing blog (SSG)
│   │   └── [slug]/
│   │       └── page.tsx                  # Post blog (SSG)
│   │
│   ├── precos/
│   │   └── page.tsx                      # Pricing (SSG, rebuild no deploy)
│   │
│   ├── glossario/
│   │   └── page.tsx                      # Glossario com anchors (SSG)
│   │
│   ├── regulacoes/
│   │   └── page.tsx                      # Timeline regulatoria (SSG)
│   │
│   ├── casos/
│   │   ├── page.tsx                      # Listing case studies (SSG)
│   │   └── [slug]/
│   │       └── page.tsx                  # Case study individual (SSG)
│   │
│   ├── ferramentas/
│   │   ├── diagnostico-compliance/
│   │   │   └── page.tsx                  # Quiz interativo (SSG + client JS)
│   │   ├── calculadora-emissoes/
│   │   │   └── page.tsx                  # Calculadora GEE (SSG + client JS)
│   │   └── gerador-pgrs/
│   │       └── page.tsx                  # Gerador basico (SSG + client JS)
│   │
│   ├── sobre/
│   │   └── page.tsx                      # Institucional (SSG)
│   │
│   ├── obrigado/
│   │   └── page.tsx                      # Thank-you page pos-form (SSG)
│   │
│   └── busca/
│       └── page.tsx                      # Pagefind search (Mes 4+, SSG + client JS)
│
├── content/                              # MDX (Git-managed)
│   ├── pgrs/
│   │   ├── index.mdx                     # Frontmatter do pilar
│   │   ├── pgrs-pgrss-diferenca.mdx
│   │   ├── pgrs-cetesb-sao-paulo.mdx    # Estadual
│   │   └── ...
│   ├── inventario-carbono/
│   │   ├── index.mdx
│   │   └── ...
│   ├── relatorio-sustentabilidade/
│   │   ├── index.mdx
│   │   └── ...
│   ├── setoriais/
│   ├── blog/
│   ├── casos/
│   └── glossario/
│       └── termos.json                   # Lista de termos para auto-link (R9)
│
├── components/
│   ├── mdx/
│   │   ├── CTA.tsx                       # CTA button (contextual)
│   │   ├── FAQ.tsx                       # Accordion FAQ
│   │   ├── InfoBox.tsx                   # Caixa de destaque regulatorio
│   │   ├── ProofBox.tsx                  # Social proof com dado + fonte
│   │   ├── PriceTable.tsx                # Tabela de precos comparativa
│   │   ├── TOC.tsx                       # Table of contents auto-gerado
│   │   ├── ArticleMeta.tsx              # Data, autor, tempo de leitura
│   │   ├── UpdateHistory.tsx             # Historico de atualizacoes (pilares)
│   │   └── GlossaryLink.tsx             # Auto-link para glossario
│   ├── layout/
│   │   ├── Header.tsx
│   │   ├── Footer.tsx
│   │   ├── Breadcrumbs.tsx
│   │   ├── WhatsAppButton.tsx            # Floating button
│   │   └── MobileCTABar.tsx              # Sticky bottom CTA (mobile)
│   ├── ui/
│   │   ├── Button.tsx
│   │   ├── Badge.tsx
│   │   ├── Card.tsx
│   │   └── Modal.tsx                     # Lazy-loaded (dynamic import)
│   ├── forms/
│   │   ├── IntakeForm.tsx                # Formulario principal (5 campos)
│   │   └── LeadMagnetGate.tsx            # Form gate para lead magnets (3 campos)
│   └── seo/
│       ├── JsonLd.tsx                    # Server Component generico JSON-LD
│       └── SchemaTemplates.ts            # Funcoes geradoras por tipo de pagina
│
├── lib/
│   ├── content.ts                        # MDX reader + frontmatter parser
│   ├── schema.ts                         # JSON-LD generators (tipados)
│   ├── metadata.ts                       # generateMetadata helpers
│   ├── glossary.ts                       # Auto-link glossario (R9)
│   ├── lead-score.ts                     # Calculo de lead score (shared types)
│   └── constants.ts                      # URLs, limites, configs
│
├── functions/                            # Cloud Functions for Firebase
│   ├── src/
│   │   ├── index.ts                      # Entry point (exports)
│   │   ├── ogImage.ts                    # OG image generator (satori + sharp)
│   │   ├── formHandler.ts                # Form submission → Firestore + notification
│   │   ├── leadScorer.ts                 # Scheduled: calcula lead scores
│   │   └── rebuildTrigger.ts             # Webhook → GitHub Actions rebuild
│   ├── package.json
│   └── tsconfig.json
│
├── public/
│   ├── images/
│   │   ├── logo.png
│   │   ├── logo.svg
│   │   └── og-default.png                # Fallback OG image
│   └── downloads/
│       ├── checklist-pgrs.pdf             # Lead magnet PGRS
│       ├── template-gri.docx              # Lead magnet RS
│       └── relatorios-setoriais/          # PDFs setoriais publicos
│
├── scripts/
│   ├── validate-content.ts               # CI: validacao MDX (frontmatter, word count, links)
│   ├── generate-search-index.ts          # Pagefind index generation
│   └── check-glossary-terms.ts           # Verifica termos novos vs. glossario
│
├── styles/
│   └── globals.css                        # Tailwind directives + custom utilities
│
├── firebase.json                          # Hosting config, rewrites, headers
├── .firebaserc                            # Project aliases (prod/staging)
├── firestore.rules                        # Security rules para leads collection
├── firestore.indexes.json                 # Indices Firestore
├── next.config.ts                         # Next.js config (MDX, images, etc.)
├── tailwind.config.ts
├── tsconfig.json
├── package.json
└── middleware.ts                           # X-Robots-Tag, redirects, preview mode
```

#### firebase.json (configuracao de referencia)

```json
{
  "hosting": {
    "public": "out",
    "cleanUrls": true,
    "trailingSlash": true,
    "ignore": ["firebase.json", "**/.*", "**/node_modules/**"],
    "rewrites": [
      {
        "source": "/og/**",
        "function": "ogImage"
      },
      {
        "source": "/api/form",
        "function": "formHandler"
      }
    ],
    "headers": [
      {
        "source": "**/*.@(js|css|svg|png|webp|woff2)",
        "headers": [
          {
            "key": "Cache-Control",
            "value": "public, max-age=31536000, immutable"
          }
        ]
      },
      {
        "source": "**/*.html",
        "headers": [
          {
            "key": "Cache-Control",
            "value": "public, max-age=3600"
          }
        ]
      },
      {
        "source": "/og/**",
        "headers": [
          {
            "key": "Cache-Control",
            "value": "public, max-age=604800"
          }
        ]
      }
    ]
  },
  "functions": {
    "source": "functions",
    "runtime": "nodejs20"
  },
  "firestore": {
    "rules": "firestore.rules",
    "indexes": "firestore.indexes.json"
  }
}
```

---

## SECAO 11: KPIs e Monitoramento v2.0

### 11.1 KPIs Organicos (SEO)

| KPI | Mes 3 | Mes 6 | Mes 12 | Fonte |
|---|---|---|---|---|
| Posicao media GSC (keywords target) | Top 20 pilares | Top 10 | Top 3 prioritarias | GSC |
| Impressoes organicas | 5.000+ | 25.000+ | 100.000+ | GSC |
| Cliques organicos | 300+ | 1.500+ | 6.000+ | GSC |
| CTR medio | >3% | >4% | >5% | GSC |
| Paginas indexadas | 20+ | 45+ | 80+ | GSC |
| Backlinks externos (dominios unicos) | 5+ | 20+ | 60+ | Ahrefs |
| Tempo medio na pagina | 2min+ | 3min+ | 3.5min+ | GA4 |
| Paginas/sessao | 1.5+ | 2.0+ | 2.5+ | GA4 |

### 11.2 KPIs de Conversao

| KPI | Mes 3 | Mes 6 | Mes 12 | Fonte |
|---|---|---|---|---|
| Leads organicos/mes | **3** (300 clicks x 1% CVR) | **30** (1.500 x 2%) | **180** (6.000 x 3%) | GA4 + Firestore |
| Leads total (todos canais)/mes | 15+ | 60+ | 250+ | Firestore |
| Lead magnet downloads/mes | 10+ | 40+ | 120+ | Brevo |
| Email nurture open rate | >25% | >30% | >30% | Brevo |
| Email nurture click rate | >3% | >5% | >5% | Brevo |
| WhatsApp clicks/mes | 20+ | 80+ | 200+ | PostHog |
| Form submissions/mes | 5+ | 25+ | 80+ | Firestore |

**Nota sobre a matematica corrigida**: 300 cliques/mes com CVR de 1% = **3 leads**, nao 10. A projecao original era otimista demais. Leads significativos via SEO so a partir do Mes 6+. Por isso, multi-channel e essencial desde o Dia 1.

### 11.3 KPIs de Receita

| KPI | Mes 3 | Mes 6 | Mes 12 | Fonte |
|---|---|---|---|---|
| MQL (Marketing Qualified Leads)/mes | 10+ | 40+ | 150+ | Lead scoring |
| MQL→SQL rate | 30%+ | 40%+ | 50%+ | CRM/Firestore |
| SQL→Cliente rate | 20%+ | 25%+ | 30%+ | CRM/Firestore |
| Ticket medio | R$1.200 | R$1.400 | R$1.600 | Financeiro |
| Receita mensal | **R$7.000** | **R$18.000** | **R$55.000** | Financeiro |
| Receita recorrente (renovacoes) | R$0 | R$500 | R$5.000 | Financeiro |
| CAC medio (todos canais) | R$200 | R$150 | R$100 | Financeiro |
| LTV/CAC ratio | 4x+ | 6x+ | 10x+ | Financeiro |

### 11.4 KPIs Multi-Channel

| KPI | Mes 3 | Mes 6 | Mes 12 | Fonte |
|---|---|---|---|---|
| Leads outbound (contadores) | 5+ | 15+ | 30+ | CRM |
| Leads Google Ads | 5+ | 15+ | 40+ | Google Ads |
| Leads marketplace (GetNinjas) | 3+ | 8+ | 15+ | Marketplace |
| Leads partner referral | 0 | 5+ | 20+ | CRM |
| Google Ads ROAS | 2x+ | 3x+ | 4x+ | Google Ads + Financeiro |
| Partner referral revenue share | R$0 | R$1.000+ | R$5.000+ | Financeiro |

### 11.5 KPIs Tecnicos

| KPI | Target | Frequencia | Fonte |
|---|---|---|---|
| LCP (p75) | < 2.5s | Continuo | Firebase Performance / CrUX |
| INP (p75) | < 150ms | Continuo | Firebase Performance / CrUX |
| CLS (p75) | < 0.1 | Continuo | Firebase Performance / CrUX |
| TTFB (p75) | < 600ms | Continuo | Firebase Performance / CrUX |
| Lighthouse Mobile Performance | >= 90 | Cada PR | Lighthouse CI |
| Lighthouse SEO | >= 98 | Cada PR | Lighthouse CI |
| Links quebrados | 0 | Semanal | Broken link checker |
| Erros de indexacao | 0 | Diario | GSC |

### 11.6 Rotina de Monitoramento

#### Diaria (5 min)
- Verificar erros de indexacao no GSC (cobertura)
- Checar notificacoes de leads hot (WhatsApp/email)
- Verificar uptime do site (Firebase console)

#### Semanal (20 min)
- Top 10 keywords: posicao atual vs. semana anterior
- Leads novos: score, origem, follow-up status
- Lead scoring review: algum lead mudou de faixa?
- WhatsApp response time audit: todas as mensagens respondidas em <2h?
- Volume de erros 404 (GSC)

#### Mensal (1h)
- Relatorio completo: impressoes, cliques, CTR, leads por UTM source
- A/B test results: qual variante venceu, proximo teste na fila
- Email sequence performance: open rate, click rate, unsubscribe por sequencia
- Pipeline de parceiros: novos parceiros contatados, deals fechados
- Revenue breakdown por canal e por servico
- Content performance: artigos com melhor CTR, piores bounce rates

#### Trimestral (3h)
- Auditoria de linkagem interna (Screaming Frog)
- Update dos 3 pilares (correcoes, novos links, dados atualizados)
- Revisao de CTAs (baseado em dados de A/B tests)
- Analise de cannibalizacao (GSC: mesma query, multiplas paginas)
- Renovacao de lead magnets (atualizar dados, melhorar design)
- Review de precos vs. mercado

#### Semestral (1 dia)
- Re-pesquisa completa de keywords (novos termos, volumes atualizados)
- Mapeamento de novos termos regulatorios (leis aprovadas no semestre)
- Auditoria de concorrentes (novos entrantes, mudancas de posicionamento)
- Revisao da estrategia de conteudo (quais clusters cresceram mais, onde investir)
- Refresh dos artigos com dateModified > 6 meses sem update

---

## SECAO 12: Go-to-Market v2.0

### 12.1 Channel Strategy (multi-channel desde o Dia 1)

| # | Canal | CAC Est. | Time to First Sale | Prioridade | Budget Mensal | Justificativa |
|---|---|---|---|---|---|---|
| 1 | **Outbound contadores** | R$0 | 2-4 semanas | #1 | Tempo (10h/sem) | CAC zero, contadores tem carteira de PMEs prontas, comissao so no fechamento |
| 2 | **Google Ads (high-intent)** | R$50-150/lead | 1-2 semanas | #2 | R$500-1.000 | Keywords transacionais ("fazer PGRS", "inventario carbono empresa") tem alta conversao |
| 3 | **Content/SEO (organico)** | R$0 | 3-6 meses | #3 (compound) | Tempo (20h/sem) | Retorno crescente, ativo que se valoriza, fundacao de longo prazo |
| 4 | **PLG tools (calculadora, diagnostico)** | R$0 | 1-3 meses | #4 | Dev time (40h total) | Captura email qualificado, demonstra competencia, viral potential |
| 5 | **Marketplaces (GetNinjas, Workana)** | 15-20% comissao | 1 semana | #5 | Comissao | Zero investimento upfront, volume alto, leads ja com intencao de compra |
| 6 | **LinkedIn Ads** | R$80-200/lead | 2-4 semanas | #6 | R$300-500 | Targeting por cargo (gerente operacoes, compliance, RH) e setor. Teste a partir do Mes 2 |
| 7 | **Partner referral program** | R$100-200/referral | Mes 2+ | #7 | Comissao | Custo zero ate converter. Escala com numero de parceiros |

**Principio**: nenhum canal sozinho sustenta o negocio nos primeiros 6 meses. A combinacao de outbound (receita rapida) + ads (volume previsivel) + SEO (crescimento composto) + PLG (qualificacao automatica) cria resiliencia.

### 12.2 Partnership Ecosystem (com timeline)

#### Tier 1 — Semana 1-2 (prioridade maxima)

**Contadores e Escritorios Contabeis**
- Modelo: 15-20% de comissao sobre servico fechado via indicacao
- Abordagem: lista de 50 escritorios no LinkedIn/Google Maps (BH, SP, RJ). Email frio + ligacao. Script: "Seus clientes PME provavelmente precisam de PGRS e nao sabem. Nos resolvemos, voce ganha comissao."
- Entregavel: material de 1 pagina explicando os 3 servicos + tabela de comissoes
- Meta Mes 1: 10 contadores contactados, 3 parceiros ativos
- Meta Mes 6: 15 parceiros ativos gerando 10+ leads/mes

**Engenheiros Ambientais Freelance**
- Modelo: 30% do valor do servico (eles fazem o trabalho tecnico, plataforma gerencia cliente e entrega)
- Abordagem: LinkedIn groups de engenharia ambiental, CRQ/CREA regionais, WhatsApp groups
- Vantagem: resolve o problema do RT (B1.1) — eles trazem a ART, plataforma traz o cliente
- Meta Mes 1: 3 engenheiros parceiros (1 por estado: SP, MG, RJ)

#### Tier 2 — Mes 2-3

**Advocacia Ambiental**
- Modelo: 15% referral fee
- Abordagem: advogados ambientais frequentemente sao consultados por clientes que precisam de PGRS/GEE para evitar multas. Parceria natural.
- Acao: identificar 10 escritorios de advocacia ambiental, enviar email personalizado com case (quando disponivel)

**Associacoes Empresariais (FIEMG, FIESP, ACIMINAS)**
- Modelo: pricing institucional com 10-15% desconto para associados
- Abordagem: propor workshop gratuito ou webinar sobre "Compliance Ambiental para PMEs" como porta de entrada
- Acao Mes 3: contato formal com FIEMG (BH) para workshop piloto

#### Tier 3 — Mes 4-6

**Consultorias ISO 14001**
- Modelo: white-label com 40% desconto (eles revendem como servico proprio)
- Justificativa: ISO 14001 exige PGRS e monitoramento de emissoes — servico complementar
- Acao: mapear 5 consultorias ISO em MG/SP, propor parceria white-label

**Consultorias de RH/ESG**
- Modelo: referral fee 15%
- Justificativa: consultorias de RH/D&I cada vez mais incluem ESG em seus pacotes
- Acao: networking em eventos de RH/sustentabilidade

### 12.3 Pricing Strategy v2.0 (tiered + recorrente)

#### Tabela de Precos por Servico e Tier

| Servico | Standard (10 dias) | Express (5 dias) | Urgente (48h) | Renovacao Anual |
|---|---|---|---|---|
| **PGRS** | R$990 | R$1.490 | R$2.490 | R$490 |
| **Inventario GEE** | R$1.290 | R$1.790 | R$2.990 | R$690 |
| **Relatorio RS** | R$1.490 | R$1.990 | R$2.990 | R$790 |
| **Bundle (PGRS+GEE+RS)** | R$2.990 (-20%) | R$4.290 (-19%) | R$6.990 (-17%) | R$1.490 (-24%) |

#### Ancoragem e Upsell
- Exibir sempre os 3 tiers lado a lado (ancoragem: urgente faz standard parecer barato)
- Destaque visual no tier Express (most popular)
- Bundle destacado como "Economize ate 24%"
- Renovacao anual mencionada em todo artigo de "renovacao PGRS" e no email pos-venda

#### Receita Recorrente
- Renovacao anual obrigatoria para PGRS (Lei 12.305, empresas com licenciamento)
- Renovacao GEE (inventario anual, ano-base anterior)
- Update de RS (novo periodo reportado)
- **Meta Mes 12**: 30% da receita vinda de renovacoes

#### Descontos Estrategicos
- Parceiro contador: cliente indicado recebe 5% desconto (incentivo para fechar)
- Associacao/institucional: 10-15% desconto
- Primeiro servico + segundo: 15% no segundo
- Pagamento a vista (PIX): 5% desconto

### 12.4 PLG Tools Roadmap

#### Ferramenta 1 — Auto-Diagnostico de Compliance (Mes 1)

**URL**: `/ferramentas/diagnostico-compliance/`

**Descricao**: Quiz de 15 perguntas que avalia se a empresa tem obrigacao legal de compliance ambiental e quais documentos precisa.

**Perguntas-chave**:
- Qual o setor da empresa? (dropdown CNAE simplificado)
- Quantos funcionarios? (range)
- A empresa gera residuos perigosos (classe I)? (sim/nao/nao sei)
- Volume diario de residuos? (range em litros)
- Em qual estado opera? (dropdown — para limiares estaduais)
- Possui licenca ambiental? (sim/nao/em processo)
- Exporta produtos? (sim/nao — trigger CBAM)
- Fornece para empresas de capital aberto? (sim/nao — trigger RS)

**Output**: checklist personalizado com:
- "OBRIGATORIO: PGRS (baseado em [lei] [limiar do municipio])"
- "RECOMENDADO: Inventario GEE (supply chain, nao obrigatorio)"
- "OPCIONAL: Relatorio RS (diferencial competitivo)"
- Proximo passo: CTA para servico relevante + lead magnet

**Gate**: resultado parcial gratuito. Resultado completo em PDF: exige email + CNAE.
**Conversao esperada**: 5-15% (email capture)

#### Ferramenta 2 — Calculadora de Emissoes GEE (Mes 2)

**URL**: `/ferramentas/calculadora-emissoes/`

**Descricao**: calculadora simplificada que estima emissoes de CO2 equivalente por escopo.

**Inputs**:
- Escopo 1: consumo de combustivel (tipo + litros/mes), refrigerantes (tipo + kg)
- Escopo 2: consumo de energia eletrica (kWh/mes), distribuidora
- Escopo 3 simplificado: viagens aereas (km/ano), transporte de carga (km/ano)

**Output**: estimativa em tCO2e/ano por escopo. Grafico visual. Comparativo com media do setor.

**Gate**: resultado na tela gratuito. PDF com detalhamento e recomendacoes: exige email.
**Conversao esperada**: 8-20% (email capture)
**Upsell**: "Este e uma estimativa simplificada. Para um inventario profissional certificavel com metodologia GHG Protocol, a partir de R$1.290"

#### Ferramenta 3 — Gerador de PGRS Basico (Mes 4)

**URL**: `/ferramentas/gerador-pgrs/`

**Descricao**: questionario guiado que gera um outline simplificado de PGRS.

**Inputs**: 20 perguntas sobre: identificacao da empresa, atividades geradoras, tipos de residuos, armazenamento, transporte, destinacao.

**Output**: outline de PGRS com 5-6 secoes preenchidas parcialmente.

**Gate**: outline na tela gratuito. Download em DOCX: exige email + telefone.
**Conversao esperada**: 10-25%
**Upsell**: "Este outline cobre ~30% de um PGRS valido. Para o documento completo, revisado por RT habilitado e pronto para protocolar, a partir de R$990"

### 12.5 Revenue Projections

#### Cenario A — Content-Only (apenas SEO organico)

| Mes | Trafego Org. | CVR | Leads | Close Rate | Ticket Medio | Receita |
|---|---|---|---|---|---|---|
| 1 | 50 | 0.5% | 0 | - | - | R$0 |
| 2 | 150 | 0.5% | 1 | 20% | R$990 | R$200 |
| 3 | 300 | 1% | 3 | 20% | R$1.100 | R$660 |
| 6 | 1.500 | 1.5% | 23 | 22% | R$1.200 | R$6.072 |
| 9 | 3.500 | 2% | 70 | 25% | R$1.300 | R$22.750 |
| 12 | 6.000 | 2.5% | 150 | 28% | R$1.400 | R$58.800 |

**Receita acumulada 12 meses (Cenario A)**: ~R$140.000
**Break-even**: Mes 5-6 (considerando custos operacionais minimos de R$3.000/mes)

#### Cenario B — Multi-Channel (recomendado)

| Mes | Leads Org. | Leads Outbound | Leads Ads | Leads PLG | Leads Mktplace | Leads Partner | Total Leads | Close Rate | Ticket Medio | Receita |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | 0 | 3 | 5 | 0 | 2 | 0 | 10 | 20% | R$1.100 | R$2.200 |
| 2 | 0 | 5 | 8 | 2 | 3 | 0 | 18 | 22% | R$1.150 | R$4.554 |
| 3 | 3 | 8 | 10 | 5 | 4 | 2 | 32 | 22% | R$1.200 | R$8.448 |
| 6 | 23 | 15 | 15 | 12 | 6 | 8 | 79 | 25% | R$1.300 | R$25.675 |
| 9 | 50 | 18 | 18 | 18 | 8 | 15 | 127 | 27% | R$1.400 | R$47.998 |
| 12 | 150 | 20 | 20 | 25 | 10 | 25 | 250 | 30% | R$1.500 | R$112.500 |

**Receita acumulada 12 meses (Cenario B)**: ~R$380.000
**Break-even**: Mes 1-2

#### Comparativo Resumido

| Metrica | Cenario A (Content-Only) | Cenario B (Multi-Channel) |
|---|---|---|
| Receita Mes 3 | R$660 | **R$8.448** |
| Receita Mes 6 | R$6.072 | **R$25.675** |
| Receita Mes 12 | R$58.800 | **R$112.500** |
| Receita acumulada 12m | R$140.000 | **R$380.000** |
| Break-even | Mes 5-6 | Mes 1-2 |
| Risco de caixa negativo | Alto (Mes 1-5) | Baixo |
| Investimento mensal Ads | R$0 | R$500-1.000 |

**Recomendacao**: Cenario B. O investimento adicional de R$500-1.000/mes em Ads se paga no primeiro lead convertido. Outbound e marketplaces sao custo zero alem de tempo.

### 12.6 Risk Mitigation Matrix

| # | Risco | Probabilidade | Impacto | Mitigacao | Trigger para Acao |
|---|---|---|---|---|---|
| 1 | **AI Overviews canibalizam cliques organicos** | Alta (60%) | Medio | Conteudo focado em transacao (nao informacao pura). PLG tools que exigem interacao. Schema markup robusto para features snippets. Diversificar canais (nao depender so de SEO) | CTR organico cai >20% em 2 meses consecutivos |
| 2 | **Entrada de concorrente VC-backed** | Media (40%) | Alto | First-mover advantage em nicho PME. Relacionamento direto com contadores. Especializacao vertical (nao generalista). Precos competitivos que VC nao sustenta | Concorrente aparece com >R$1M investido no segmento |
| 3 | **Mudanca regulatoria major (novo decreto SBCE, alteracao Lei 12.305)** | Alta (70%) | Medio-Alto | Content freshness strategy (72h update trigger). Monitoramento DOU semanal. RT parceiro com acesso a previews regulatorios via CRQ/CREA | Nova regulacao publicada no DOU |
| 4 | **Bottleneck de capacidade (demanda > oferta)** | Media (30%) | Alto | Rede de engenheiros parceiros (escala horizontal). Tiers de entrega (Standard/Express/Urgente). Waitlist transparente no site. Priorizar bundle (maior ticket, mesmo esforco) | Lead time excede 15 dias uteis |
| 5 | **RT (Responsavel Tecnico) nao encontrado ou sai** | Media (40%) | Critico | Nunca depender de 1 RT. Manter 2-3 engenheiros parceiros. Contrato com clausula de transicao de 60 dias. Fee por documento (nao retainer) reduz risco financeiro | RT principal informa saida |
| 6 | **Google penalty (over-optimization, thin content)** | Baixa (15%) | Alto | Seguir E-E-A-T rigorosamente. Nao publicar conteudo thin (<1.500 palavras). FAQ schema limitado a 5 perguntas em satelites. Audit trimestral de linkagem. Diversificar trafego (ads, social, email) | Queda >50% de trafego organico em 1 semana |
| 7 | **Brevo/PostHog descontinuam free tier** | Baixa (10%) | Baixo | Exportar dados regularmente. Alternativas mapeadas: Mailchimp (free 500 contacts), Plausible (self-hosted analytics). Custo upgrade Brevo: ~R$25/mes | Anuncio de mudanca de pricing |
| 8 | **PMEs nao percebem valor (mercado frio)** | Media (35%) | Alto | Conteudo TOFU educacional (B2.2). Framing "quanto custa NAO ter". Calculadora ROI. Cases com numeros reais. Parcerias com contadores (trusted advisor) | CVR < 0.5% apos 3 meses com trafego |

### 12.7 Proximos Passos Imediatos (Semana 1)

| # | Acao | Owner | Prazo | Dependencia | Entregavel |
|---|---|---|---|---|---|
| 1 | **Resolver licenciamento profissional (RT)** — Contatar 5 engenheiros ambientais freelance para parceria fee-por-documento | Fundador | Dia 1-3 | **BLOQUEIA conteudo e servicos** | Carta de intencao assinada com pelo menos 1 RT |
| 2 | **Definir modelo de receita** — Hibrido recomendado: tiers Standard/Express/Urgente (done-for-you) + ferramentas PLG (self-service parcial) | Fundador | Dia 1-2 | Nenhuma | Documento 1 pagina com tiers, precos, modelo |
| 3 | **Configurar repo paloma** — Next.js 15 + App Router + Tailwind + Firebase Hosting + Cloud Functions. Deploy hello world. | Dev | Dia 1-3 | Nenhuma | Site live em Firebase com pagina placeholder |
| 4 | **Configurar WhatsApp Business** — Numero dedicado, foto perfil profissional, mensagem automatica, catalogo de servicos | Fundador | Dia 2 | Nenhuma | WhatsApp Business ativo com auto-reply |
| 5 | **Implementar floating WhatsApp button** — Componente React com mensagens pre-preenchidas por rota | Dev | Dia 3-4 | #3 | Componente deployado |
| 6 | **Iniciar outbound para contadores** — Lista de 20 escritorios contabeis (BH + SP). Email frio personalizado + follow-up em 3 dias | Fundador | Dia 3-5 | #2 | 20 emails enviados, tracking de respostas |
| 7 | **Listar servicos em GetNinjas + Workana** — Perfil completo, portfolio (mesmo sem cases, descrever metodologia), precos | Fundador | Dia 3-4 | #2 | Perfis ativos e verificados |
| 8 | **Criar lead magnet PGRS** — Checklist "Sua empresa precisa de PGRS?" em PDF (3-5 paginas, design Canva) | Fundador | Dia 4-5 | Nenhuma | PDF pronto para download |
| 9 | **Configurar Brevo** — Conta free, listas por cluster (PGRS/GEE/RS), template base de email, formulario de intake (integravel com site) | Dev | Dia 4-5 | Nenhuma | Brevo configurado com 1 automacao de welcome |
| 10 | **Escrever artigo urgencia SBCE** — Primeiro conteudo publicado. Lei 15.042/2024, framing correto (regulamentacao pendente), E-E-A-T com credenciais do RT | Fundador + RT | Dia 5-7 | **#1** (precisa do RT para E-E-A-T) | Artigo publicado e submetido ao GSC |
| 11 | **Configurar Google Ads** — Conta, keywords high-intent (5-10 termos: "fazer pgrs", "inventario carbono empresa", "relatorio sustentabilidade"), budget R$30/dia, landing page = `/precos/` ou pilar | Fundador | Dia 5-7 | #3, pagina de precos minima | Campanha ativa com tracking de conversao |
| 12 | **Configurar PostHog** — Conta free, instalar SDK, eventos basicos (page_view, cta_click, form_submit, whatsapp_click) | Dev | Dia 5-7 | #3 | Analytics ativo com dashboard basico |

**Checkpoint Semana 1**: RT parceiro confirmado, site no ar (placeholder), WhatsApp ativo, 20 contadores contactados, Brevo configurado, primeiro artigo em producao.

**Checkpoint Semana 2**: Primeiro artigo publicado, Google Ads rodando, 2+ leads de marketplace/outbound, lead magnet disponivel para download, PostHog trackeando eventos.

---

*Plano de Conteudo SEO v2.0 — Secoes 7-12. Incorpora 50+ recomendacoes do painel de 6 especialistas. Documento complementar as Secoes 1-6.*
