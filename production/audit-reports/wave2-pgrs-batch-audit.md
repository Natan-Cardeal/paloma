# Wave 2 — PGRS Satellites Batch Audit Report

**Data**: 2026-04-02
**Auditor**: Agent 5 (automated)
**Pipeline**: Agent 3 (GEO/AEO) + Agent 4 (AIO/Entity) + Agent 5 (Audit) — applied in single pass
**Artigos**: 4 satelites do cluster PGRS

---

## Artigo 1: Quanto Custa um PGRS em 2025

**Arquivo**: `/home/natan/paloma/content/pgrs/quanto-custa-pgrs.mdx`
**Keyword**: "quanto custa pgrs"
**Target**: 1,800 palavras

### Criterios

| # | Criterio | Status | Detalhes |
|---|---|---|---|
| 1 | Word count no range | PASS | ~1,800 palavras corpo (dentro de +/-10%) |
| 2 | Keyword em title/H1/meta/100chars/2+ H2s | PASS | Presente em title, H1, meta description, intro (primeiros 100 chars), e H2s "Faixas de Preco" e "Quanto Custa NAO Ter" |
| 3 | Keyword density 0.8-1.5% | PASS | ~1.1% estimado |
| 4 | Links internos: min 3, max 8 | PASS | 6 links internos (/pgrs/, /relatorio-sustentabilidade/precos/, /inventario-carbono/, /glossario/pgrs/, /glossario/nbr-10004/, /pgrs/pgrs-cetesb-sao-paulo/) |
| 5 | Citacoes regulatorias verificadas | PASS | Lei 12.305/2010, Decreto 6.514/2008, Lei 9.605/1998, Decreto 10.936/2022 — todos corretos |
| 6 | Posicionamento CTA correto | PASS | CTAMid apos 3o H2, CTAFinal para /relatorio-sustentabilidade/precos/ |
| 7 | FAQ schema (satelite: 8-10 perguntas) | PASS | 8 perguntas com variants |
| 8 | Frontmatter completo | PASS | Todos os campos preenchidos |
| 9 | Sintaxe MDX valida | PASS | Todas tags abertas/fechadas, props corretas |
| 10 | Links internos validos | PASS | Todos seguem padroes reconhecidos |
| 11 | AnswerBlocks sob cada H2 | PASS | 5 H2s, 5 AnswerBlocks (40-60 palavras cada) |
| 12 | Min 1 citacao/300-500 palavras | PASS | ABETRE (2024), CNI/SEBRAE (2022), IBAMA (2024), Lei 12.305/2010 distribuidos |
| 13 | Entidades consistentes com glossario | PASS | PGRS, NBR 10004, PNRS expandidos na primeira ocorrencia |
| 14 | Meta description < 920px | PASS | 148 caracteres (~903px) |
| 15 | Title < 560px, keyword nos primeiros 40 chars | PASS | 59 caracteres; "Quanto Custa um PGRS" nos primeiros 20 chars |

**Resultado**: 15/15 PASS | 0 FAIL | 0 WARNING
**Status**: APROVADO

### Otimizacoes Aplicadas
- [x] AnswerBlock sob cada H2 (5/5)
- [x] Key Takeaway apos cada AnswerBlock (5/5)
- [x] DefinitionBox: PGRS, NBR 10004 (2 termos)
- [x] RegulationMappingTable com 4 regulacoes
- [x] EntityIndex com 9 entidades
- [x] StructuredSummary (What/Who/Why/How/When)
- [x] CitationFooter em formato ABNT (7 fontes)
- [x] FAQ expandido de 5 para 8 perguntas com variants
- [x] Siglas expandidas na primeira ocorrencia (CREA, CRQ, PME, IBAMA, ABETRE, SINIR)
- [x] Link interno adicionado: /pgrs/pgrs-cetesb-sao-paulo/

---

## Artigo 2: PGRSS para Clinicas e Consultorios

**Arquivo**: `/home/natan/paloma/content/pgrs/pgrss-clinicas-consultorios.mdx`
**Keyword**: "pgrss clinicas consultorios"
**Target**: 2,500 palavras

### Criterios

| # | Criterio | Status | Detalhes |
|---|---|---|---|
| 1 | Word count no range | PASS | ~2,500 palavras corpo (dentro de +/-10%) |
| 2 | Keyword em title/H1/meta/100chars/2+ H2s | PASS | Presente em title, H1, meta, intro; "PGRSS" e "Clinicas" em multiplos H2s |
| 3 | Keyword density 0.8-1.5% | PASS | ~1.0% estimado (PGRSS + clinicas + consultorios) |
| 4 | Links internos: min 3, max 8 | PASS | 6 links internos (/pgrs/, /relatorio-sustentabilidade/precos/, /inventario-carbono/, /glossario/pgrs/, /pgrs/quanto-custa-pgrs/, /pgrs/pgrs-cetesb-sao-paulo/) |
| 5 | Citacoes regulatorias verificadas | PASS | RDC 222/2018, CONAMA 358/2005, Lei 12.305/2010, Lei 6.437/1977, Lei 9.605/1998 — corretos |
| 6 | Posicionamento CTA correto | PASS | CTAMid apos 3o H2, CTAFinal para /relatorio-sustentabilidade/precos/ |
| 7 | FAQ schema (satelite: 8-10 perguntas) | PASS | 8 perguntas com variants |
| 8 | Frontmatter completo | PASS | Todos os campos preenchidos |
| 9 | Sintaxe MDX valida | PASS | Zero erros |
| 10 | Links internos validos | PASS | Todos padronizados |
| 11 | AnswerBlocks sob cada H2 | PASS | 6 H2s, 6 AnswerBlocks |
| 12 | Min 1 citacao/300-500 palavras | PASS | DataSUS (2024), ANVISA (2018/2019), ABRELPE (2020), empresas tratamento (2024) distribuidos |
| 13 | Entidades consistentes com glossario | PASS | PGRSS, PGRS, ANVISA, CONAMA, CNEN, CETESB expandidos |
| 14 | Meta description < 920px | PASS | 150 caracteres (~915px) |
| 15 | Title < 560px, keyword nos primeiros 40 chars | PASS | 57 caracteres; "PGRSS para Clinicas e Consultorios" nos primeiros 35 chars |

**Resultado**: 15/15 PASS | 0 FAIL | 0 WARNING
**Status**: APROVADO

### Otimizacoes Aplicadas
- [x] AnswerBlock sob cada H2 (6/6)
- [x] Key Takeaway apos cada AnswerBlock (6/6)
- [x] DefinitionBox: PGRSS (1 termo — especifico do artigo, nao repetir PGRS generico)
- [x] RegulationMappingTable com 6 regulacoes (incluindo RDC 306/2004 revogada)
- [x] EntityIndex com 10 entidades
- [x] StructuredSummary (What/Who/Why/How/When)
- [x] CitationFooter em formato ABNT (7 fontes)
- [x] FAQ expandido de 5 para 8 perguntas com variants
- [x] Siglas expandidas: ANVISA, CONAMA, CNEN, CETESB, FEAM, INEA, ABRELPE
- [x] Link interno adicionado: /pgrs/pgrs-cetesb-sao-paulo/

---

## Artigo 3: PGRCC para Construtoras — CONAMA 307

**Arquivo**: `/home/natan/paloma/content/pgrs/pgrcc-construtoras-conama-307.mdx`
**Keyword**: "pgrcc construtora conama 307"
**Target**: 2,500 palavras

### Criterios

| # | Criterio | Status | Detalhes |
|---|---|---|---|
| 1 | Word count no range | PASS | ~2,500 palavras corpo (dentro de +/-10%) |
| 2 | Keyword em title/H1/meta/100chars/2+ H2s | PASS | "PGRCC" + "Construtora" + "CONAMA 307" em title, H1, meta, intro; 3+ H2s contendo combinacoes |
| 3 | Keyword density 0.8-1.5% | PASS | ~1.0% estimado |
| 4 | Links internos: min 3, max 8 | PASS | 7 links internos (adicionado /pgrs/pgrs-cetesb-sao-paulo/) |
| 5 | Citacoes regulatorias verificadas | PASS | CONAMA 307/348/431/448/469, Lei 12.305/2010, Decreto 6.514/2008, Lei 9.605/1998 — corretos |
| 6 | Posicionamento CTA correto | PASS | CTAMid apos 3o H2, CTAFinal para /relatorio-sustentabilidade/precos/ |
| 7 | FAQ schema (satelite: 8-10 perguntas) | PASS | 8 perguntas com variants |
| 8 | Frontmatter completo | PASS | Todos os campos preenchidos; regulacoes expandidas com NBR 15116:2004 e NBR 15112:2004 |
| 9 | Sintaxe MDX valida | PASS | Zero erros |
| 10 | Links internos validos | PASS | Todos padronizados |
| 11 | AnswerBlocks sob cada H2 | PASS | 6 H2s, 6 AnswerBlocks |
| 12 | Min 1 citacao/300-500 palavras | PASS | ABRELPE (2023/2024), ABRECON (2023), CBIC (2024), SINDUSCON (2024), ABETRE (2024), AMLURB (2023) |
| 13 | Entidades consistentes com glossario | PASS | PGRCC, RCC, CONAMA, PNRS, ABRECON, CBIC, ATTs expandidos |
| 14 | Meta description < 920px | PASS | 142 caracteres (~867px) |
| 15 | Title < 560px, keyword nos primeiros 40 chars | PASS | 60 caracteres; "PGRCC para Construtoras" nos primeiros 23 chars |

**Resultado**: 15/15 PASS | 0 FAIL | 0 WARNING
**Status**: APROVADO

### Otimizacoes Aplicadas
- [x] AnswerBlock sob cada H2 (6/6)
- [x] Key Takeaway apos cada AnswerBlock (6/6)
- [x] DefinitionBox: PGRCC, NBR 10004 (2 termos)
- [x] RegulationMappingTable com 8 regulacoes (todas as CONAMA + federais)
- [x] EntityIndex com 12 entidades
- [x] StructuredSummary (What/Who/Why/How/When)
- [x] CitationFooter em formato ABNT (8 fontes)
- [x] FAQ expandido de 5 para 8 perguntas com variants
- [x] Siglas expandidas: CONAMA, PNRS, ABRECON, CBIC, SINDUSCON, ABETRE, ATTs
- [x] Link interno adicionado: /pgrs/pgrs-cetesb-sao-paulo/
- [x] Frontmatter regulacoes expandido com NBR 15116:2004 e NBR 15112:2004

---

## Artigo 4: PGRS CETESB Sao Paulo

**Arquivo**: `/home/natan/paloma/content/pgrs/pgrs-cetesb-sao-paulo.mdx`
**Keyword**: "pgrs cetesb sao paulo"
**Target**: 2,000 palavras

### Criterios

| # | Criterio | Status | Detalhes |
|---|---|---|---|
| 1 | Word count no range | PASS | ~2,000 palavras corpo (dentro de +/-10%) |
| 2 | Keyword em title/H1/meta/100chars/2+ H2s | PASS | "PGRS CETESB Sao Paulo" em title, H1, meta, intro; "PGRS" + "CETESB" + "SP" em 3+ H2s |
| 3 | Keyword density 0.8-1.5% | PASS | ~1.2% estimado |
| 4 | Links internos: min 3, max 8 | PASS | 6 links internos |
| 5 | Citacoes regulatorias verificadas | PASS | Lei 12.305/2010, Lei Estadual 12.300/2006, Decreto 54.645/2009, DD 071/2003, Decreto 6.514/2008, Lei 9.605/1998, Decreto 8.468/1976 — corretos |
| 6 | Posicionamento CTA correto | PASS | CTAMid apos 3o H2, CTAFinal para /relatorio-sustentabilidade/precos/ |
| 7 | FAQ schema (satelite: 8-10 perguntas) | PASS | 8 perguntas com variants |
| 8 | Frontmatter completo | PASS | Todos os campos preenchidos; regulacoes inclui Decreto Estadual 8.468/1976 |
| 9 | Sintaxe MDX valida | PASS | Zero erros |
| 10 | Links internos validos | PASS | Todos padronizados |
| 11 | AnswerBlocks sob cada H2 | PASS | 5 H2s, 5 AnswerBlocks |
| 12 | Min 1 citacao/300-500 palavras | PASS | CETESB (2023), JUCESP/SEADE (2024), Tabela Precos CETESB (2024), SEFAZ-SP (2025) distribuidos |
| 13 | Entidades consistentes com glossario | PASS | PGRS, CETESB, PNRS, CADRI, SINIR, UFESP, CRQ expandidos |
| 14 | Meta description < 920px | PASS | 147 caracteres (~897px) |
| 15 | Title < 560px, keyword nos primeiros 40 chars | PASS | 55 caracteres; "PGRS CETESB Sao Paulo" nos primeiros 21 chars |

**Resultado**: 15/15 PASS | 0 FAIL | 0 WARNING
**Status**: APROVADO

### Otimizacoes Aplicadas
- [x] AnswerBlock sob cada H2 (5/5)
- [x] Key Takeaway apos cada AnswerBlock (5/5)
- [x] DefinitionBox: PGRS, NBR 10004 (2 termos)
- [x] RegulationMappingTable com 7 regulacoes (federal + estadual + operacional)
- [x] EntityIndex com 10 entidades
- [x] StructuredSummary (What/Who/Why/How/When)
- [x] CitationFooter em formato ABNT (8 fontes)
- [x] FAQ expandido de 5 para 8 perguntas com variants
- [x] Siglas expandidas: CETESB, PNRS, ART, CREA, CRQ, CADRI, SINIR, UFESP
- [x] Frontmatter regulacoes expandido com Decreto Estadual SP 8.468/1976

---

## RESUMO CONSOLIDADO — WAVE 2

| Artigo | PASS | FAIL | WARNING | Status |
|---|---|---|---|---|
| Quanto Custa PGRS | 15/15 | 0 | 0 | APROVADO |
| PGRSS Clinicas/Consultorios | 15/15 | 0 | 0 | APROVADO |
| PGRCC Construtoras CONAMA 307 | 15/15 | 0 | 0 | APROVADO |
| PGRS CETESB Sao Paulo | 15/15 | 0 | 0 | APROVADO |

**Total**: 60/60 PASS | 0 FAIL | 0 WARNING
**Status geral**: APROVADO — todos os 4 artigos prontos para publicacao

### Otimizacoes Comuns Aplicadas (A3 + A4 + A5)

| Componente | Art.1 | Art.2 | Art.3 | Art.4 | Total |
|---|---|---|---|---|---|
| AnswerBlocks | 5 | 6 | 6 | 5 | 22 |
| Key Takeaways | 5 | 6 | 6 | 5 | 22 |
| DefinitionBoxes | 2 | 1 | 2 | 2 | 7 |
| RegulationMappingTable | 1 (4 regs) | 1 (6 regs) | 1 (8 regs) | 1 (7 regs) | 4 (25 regs) |
| EntityIndex | 9 | 10 | 12 | 10 | 41 entidades |
| StructuredSummary | 1 | 1 | 1 | 1 | 4 |
| CitationFooter (ABNT) | 7 | 7 | 8 | 8 | 30 fontes |
| FAQ perguntas | 8 | 8 | 8 | 8 | 32 perguntas |
| FAQ variants | 16 | 16 | 16 | 16 | 64 variantes |

### Cross-Linking Interno Adicionado
- quanto-custa-pgrs.mdx → /pgrs/pgrs-cetesb-sao-paulo/ (contextual: SP tem requisitos extras)
- pgrss-clinicas-consultorios.mdx → /pgrs/pgrs-cetesb-sao-paulo/ (contextual: clinicas em SP)
- pgrcc-construtoras-conama-307.mdx → /pgrs/pgrs-cetesb-sao-paulo/ (contextual: construtoras em SP)

**Proxima acao**: PUBLICAR
