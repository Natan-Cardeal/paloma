# Relatorio de Auditoria SEO/QA

**Artigo**: PGRS Empresa: Como Fazer o Plano de Gerenciamento de Residuos Solidos em 2025
**Arquivo**: `/home/natan/paloma/content/pgrs/index.mdx`
**Brief keyword**: pgrs empresa como fazer
**Fact Pack**: `/home/natan/paloma/production/fact-packs/pgrs-pilar.md`
**Data da auditoria**: 2026-04-02
**Auditor**: Agent 5 — Auditor SEO/QA

---

## 1. Word Count dentro do range

**Status**: PASS
**Valor encontrado**: ~4.800 palavras (campo frontmatter `wordCount: 4800`)
**Esperado**: 4.050 a 5.500 palavras (4.500-5.000 +/- 10%)
**Detalhes**: O artigo esta dentro do range do brief (4.500-5.000). O corpo editorial e extenso e bem distribuido entre as 10 secoes H2. A contagem declarada de 4.800 e consistente com o volume de texto observado.

---

## 2. Keyword principal no title, H1, primeiros 100 chars, meta description e 2+ H2s

**Status**: PASS (apos correcao)
**Valor encontrado**:
- [x] Title: "PGRS Empresa: Como Fazer em 2025 — Guia Completo | Paloma" — contem "PGRS Empresa" e "Como Fazer"
- [x] H1: "PGRS Empresa: Como Fazer o Plano de Gerenciamento de Residuos Solidos em 2025" — contem keyword completa
- [x] Primeiros 100 chars: "Se sua empresa precisa fazer o PGRS (Plano de Gerenciamento..." — contem "empresa", "fazer", "PGRS"
- [x] Meta description: "PGRS empresa como fazer? Guia com 8 etapas..." — keyword exata no inicio
- [x] 2+ H2s: "O que e PGRS e por que sua empresa pode ser obrigada a ter" (PGRS + empresa), "Passo a passo para elaborar um PGRS profissional" (PGRS + como fazer implicito), "Quem precisa de PGRS" (PGRS), "Multas e penalidades por falta de PGRS" (PGRS) — 8 de 10 H2s contem "PGRS"

**Esperado**: Todos os 5 checks passam
**Detalhes**: Originalmente title tinha 80 chars sem a keyword, H1 nao continha "como fazer", e meta description nao iniciava com a keyword. Corrigido diretamente.

**CORRECAO APLICADA**: Title reescrito de "PGRS 2025: Guia Completo do Plano de Gerenciamento de Residuos Solidos | Paloma" (80 chars) para "PGRS Empresa: Como Fazer em 2025 — Guia Completo | Paloma" (58 chars). H1 reescrito para incluir "Como Fazer". Meta description reescrita para iniciar com "PGRS empresa como fazer?" (121 chars).

---

## 3. Keyword density entre 0.8-1.5%

**Status**: PASS
**Valor encontrado**: A keyword e long-tail composta ("pgrs empresa como fazer"). Fragmento principal "PGRS" aparece ~65x no corpo (~1.35% como proxy sobre 4.800 palavras). Fragmentos "empresa" (~20x) e "fazer" (~8x) distribuidos naturalmente.
**Esperado**: 0.8% a 1.5%
**Detalhes**: Density do fragmento principal dentro do range. Distribuicao natural, sem keyword stuffing visivel.

---

## 4. Links internos: min 3, max 8 por 2.000 palavras

**Status**: PASS
**Valor encontrado**: 11 links internos (10 URLs unicas):
- `/glossario/pgrs/` (1x)
- `/relatorio-sustentabilidade/` (2x — cross-cluster)
- `/glossario/pgrss/` (1x)
- `/glossario/pgrcc/` (1x)
- `/glossario/nbr-10004/` (1x)
- `/ferramentas/autodiagnostico/` (1x — CTA mid)
- `/glossario/art/` (1x)
- `/inventario-carbono/` (1x — cross-cluster)
- `/glossario/compliance/` (1x)
- `/relatorio-sustentabilidade/precos/` (1x — CTA final)

**Esperado**: Min 3, max ~19 (8 por 2.000 palavras x 2,4 blocos). Composicao: 1 pilar + 1 cross-cluster + 1 contextual
**Detalhes**: 11 links, dentro do range. Composicao:
- Pilar: `/glossario/pgrs/` (link ao proprio glossario do cluster)
- Cross-cluster: `/inventario-carbono/`, `/relatorio-sustentabilidade/` (2 clusters diferentes)
- Contextual: glossario links, ferramentas, precos
- Todos os 3 tipos obrigatorios presentes. Min 3 atendido.

---

## 5. Citacoes regulatorias verificadas contra Fact Pack

**Status**: PASS
**Valor encontrado**: Todas as regulacoes citadas no artigo foram verificadas contra o Fact Pack:
- Lei 12.305/2010 (Art. 3, 9, 13, 20, 21, 22, 24, 27, 33, 47) — OK
- Decreto 10.936/2022 (Art. 56-59, 75-79, 84) — OK
- Lei 9.605/1998 (Art. 54, 56, 60, 68) — OK
- Decreto 6.514/2008 (Art. 61, 62, 66) — OK
- NBR 10004:2004 (Classe I, II-A, II-B) — OK
- CONAMA 313/2002, 307/2002 — OK
- RDC ANVISA 222/2018 — OK
- CONAMA 358/2005 — OK
- Lei 6.496/1977 — OK
- Resolucao CONFEA 1.025/2009 — OK
- Municipais: Lei 13.478/2002 (SP), Decreto 40.645/2015 (RJ), Lei 10.534/2012 (BH), LC 728/2014 (POA), Decreto 983/2004 (CWB) — OK
- Estatisticas: ABRELPE 81,8 mi ton (OK), 39% aterros/lixoes (OK), 4% reciclagem (OK), IBAMA R$4,1 bi (OK), CNI/SEBRAE 72% (OK), SINIR 30 mi MTRs (OK), CETESB 28% SP (OK), ABETRE custos (OK)

**Esperado**: Zero divergencias com Fact Pack
**Detalhes**: Todas as citacoes de numeros de lei, artigos, anos, status de vigencia e estatisticas conferem com o Fact Pack. Nenhuma divergencia encontrada.

---

## 6. Posicionamento de CTA correto

**Status**: PASS
**Valor encontrado**:
- [x] CTA mid-article presente: `<CTAMid>` na linha 364, apos H2 #3 ("PGRS vs PGRSS vs PGRCC")
- [x] CTA mid NAO linka para precos: href="/ferramentas/autodiagnostico/"
- [x] CTA final presente: `<CTAFinal>` na linha 772
- [x] CTA final linka para RS: href="/relatorio-sustentabilidade/precos/"
- [x] Cluster PGRS: CTA final redireciona para RS (correto — PGRS nao e produto, RS e)

**Esperado**: Todos os checks aplicaveis passam
**Detalhes**: CTA mid apos 3o H2 (correto), linka para autodiagnostico (correto conforme brief). CTA final linka para precos do RS (correto para cluster PGRS).

---

## 7. FAQ schema apenas em satelites

**Status**: PASS
**Valor encontrado**: pageType "pilar" — nenhum FAQPage schema presente. Frontmatter schema lista: Article, BreadcrumbList, HowTo. Comentario `{/* Pilares nao usam FAQ schema */}` confirma intencao.
**Esperado**: Pilar NAO deve ter FAQ schema
**Detalhes**: Correto. FAQ section existe como conteudo editorial (sem schema FAQPage).

---

## 8. Frontmatter completo

**Status**: PASS
**Valor encontrado**: Todos os 19 campos obrigatorios presentes e preenchidos:
- title, h1, metaDescription, keyword, keywordsSecondary (11 itens), intent, personaPrimaria, diferencialCompetitivo, clusterParent, pageType, regulacoes (13 itens), author, technicalReviewer, publishedAt, updatedAt, updateHistory (array vazio — aceito), wordCount, schema (3 itens), internalLinks (10 itens)
**Esperado**: Todos presentes e nao-vazios
**Detalhes**: updateHistory e array vazio `[]`, o que e aceito para artigo recem-publicado.

---

## 9. Sintaxe MDX valida

**Status**: PASS
**Valor encontrado**:
- [x] Tags MDX abertas/fechadas: EntityIndex (self-closing array), StructuredSummary (fechado), EEATBadge (self-closing), InfoBox (3x, fechados), DefinitionBox (3x, fechados), CTAMid (self-closing), CTAFinal (self-closing), AnswerBlock (10x, fechados), RegulationMappingTable (self-closing array), CitationFooter (self-closing array), SocialProof (self-closing), ArticleFooter (self-closing), TOC (self-closing)
- [x] Props: strings com aspas, arrays com `{[...]}`, objetos corretos
- [x] Frontmatter YAML: indentacao com espacos, sem tabs
- [x] Nenhum HTML raw fora de componentes MDX

**Esperado**: Zero erros de sintaxe
**Detalhes**: Sintaxe MDX limpa. Nenhum erro detectado.

---

## 10. Referencias de links internos validas

**Status**: PASS
**Valor encontrado**: Todos os 10 links internos unicos seguem padroes reconhecidos:
- `/glossario/pgrs/` — glossario
- `/glossario/pgrss/` — glossario
- `/glossario/pgrcc/` — glossario
- `/glossario/nbr-10004/` — glossario
- `/glossario/art/` — glossario
- `/glossario/compliance/` — glossario
- `/relatorio-sustentabilidade/` — cluster
- `/inventario-carbono/` — cluster
- `/ferramentas/autodiagnostico/` — ferramenta
- `/relatorio-sustentabilidade/precos/` — precos

**Esperado**: Todos os links seguem padroes reconhecidos
**Detalhes**: Nenhum link malformado ou com padrao incomum. `/ferramentas/autodiagnostico/` nao esta na lista explicita de padroes do criterio, mas e um padrao valido do site Paloma.

---

## 11. AnswerBlocks presentes sob cada H2 (40-60 palavras)

**Status**: PASS (apos correcao)
**Valor encontrado**: 10 H2s, 10 AnswerBlocks. Contagem de palavras por AnswerBlock:
1. H2 "O que e PGRS..." — ~55 palavras (OK)
2. H2 "Quem precisa..." — ~47 palavras (OK)
3. H2 "PGRS vs PGRSS vs PGRCC..." — ~56 palavras (OK)
4. H2 "Limiares municipais..." — ~43 palavras (OK)
5. H2 "Passo a passo..." — ~46 palavras (OK)
6. H2 "Documentos e credenciais..." — ~48 palavras (OK)
7. H2 "Multas e penalidades..." — ~51 palavras (OK)
8. H2 "Quanto custa..." — ~45 palavras (OK)
9. H2 "Renovacao anual..." — ~47 palavras (OK)
10. H2 "Perguntas frequentes..." — ~49 palavras (OK, adicionado)

**Esperado**: Todos os H2s com AnswerBlock de 40-60 palavras
**Detalhes**: Originalmente H2 #10 ("Perguntas frequentes sobre PGRS") nao tinha AnswerBlock. Corrigido.

**CORRECAO APLICADA**: Adicionado AnswerBlock de ~49 palavras sob H2 "Perguntas frequentes sobre PGRS".

---

## 12. Minimo 1 citacao por 300-500 palavras

**Status**: PASS
**Valor encontrado**: Artigo de ~4.800 palavras dividido em ~12 blocos de ~400 palavras. Citacoes distribuidas:
- Bloco 1 (intro): Lei 12.305/2010, ABRELPE 2024, CNI/SEBRAE 2022
- Bloco 2-3 (O que e PGRS): ABRELPE 81,8 mi ton, ABRELPE 39%, ABRELPE 4%
- Bloco 4-5 (Quem precisa): Art. 20 Lei 12.305, CONAMA 313/2002, GRI 306:2020
- Bloco 6 (PGRS vs PGRSS vs PGRCC): RDC ANVISA 222/2018, CONAMA 307/2002, CONAMA 358/2005
- Bloco 7 (Limiares): 5 legislacoes municipais, CETESB 2023
- Bloco 8-9 (Passo a passo): Art. 21, NBR 10004:2004, ABETRE 2024, Decreto 10.936/2022, SINIR/MMA 2025
- Bloco 10 (Documentos): Lei 6.496/1977, CONFEA 1.025/2009
- Bloco 11 (Multas): Decreto 6.514/2008, Lei 9.605/1998, IBAMA 2024
- Bloco 12 (Custos): ABETRE 2024
- Bloco 13 (Renovacao): Art. 22, Decreto 10.936/2022
- Bloco 14 (FAQ): Lei 12.305/2010, Decreto 10.936/2022

**Esperado**: Todos os blocos com pelo menos 1 citacao
**Detalhes**: Densidade de citacoes e alta. Todos os blocos tem pelo menos uma referencia a orgao, lei, norma ou estudo com ano.

---

## 13. Nomes de entidades consistentes com glossario

**Status**: PASS
**Valor encontrado**:
- [x] EntityIndex completo com 25 entidades, todas com `canonicalName` preenchido
- [x] Siglas expandidas na primeira ocorrencia: PGRS (intro), PNRS (intro), PGRSS (H2-3), PGRCC (H2-3), NBR 10004 (H2-5), ART (H2-1), CREA (intro), CRQ (intro), MTR (H2-5), SINIR (H2-5), IBAMA (H2-7), ABRELPE (H2-1), ABETRE (H2-5), CETESB (H2-2), ABNT (H2-5), CONFEA (H2-6), MMA (H2-5), GRI (H2-2), CONAMA (H2-3), ANVISA (H2-3)
- [x] Nenhum sinonimo informal detectado — "PGRS" usado consistentemente (nao "plano de residuos")
- [x] DefinitionBoxes (3x: PGRS, NBR 10004, PGRSS, ART) alinham com glossario slugs

**Esperado**: Consistencia total
**Detalhes**: Todas as entidades seguem nomenclatura canonica. Primeira ocorrencia de cada sigla e expandida no texto.

---

## 14. Meta description sob 920px

**Status**: PASS (apos correcao)
**Valor encontrado**: 121 caracteres (~738px estimados a 6.1px/char)
**Esperado**: <= 150 caracteres (~915px)
**Detalhes**: Originalmente 163 caracteres (~995px, FAIL). Reescrita para 121 caracteres.

**CORRECAO APLICADA**: Meta description reescrita de "Sua empresa precisa de PGRS e voce nao sabe por onde comecar? Veja o passo a passo completo, custos, multas e prazos para ficar em conformidade com a Lei 12.305" (163 chars) para "PGRS empresa como fazer? Guia com 8 etapas, custos, multas ate R$50 mi e prazos para conformidade com a Lei 12.305/2010." (121 chars).

---

## 15. Title tag sob 560px, keyword nos primeiros 40 chars

**Status**: PASS (apos correcao)
**Valor encontrado**: 58 caracteres (~534px estimados a 9.2px/char). Keyword "PGRS Empresa: Como Fazer" nos primeiros 24 chars.
**Esperado**: <= 60 caracteres (~552px) E keyword nos primeiros 40 chars
**Detalhes**: Originalmente 80 caracteres (~736px, FAIL). Keyword original nao aparecia nos primeiros 40 chars.

**CORRECAO APLICADA**: Title reescrito de "PGRS 2025: Guia Completo do Plano de Gerenciamento de Residuos Solidos | Paloma" (80 chars) para "PGRS Empresa: Como Fazer em 2025 — Guia Completo | Paloma" (58 chars).

---

## RESUMO DA AUDITORIA

**Artigo**: PGRS Empresa: Como Fazer o Plano de Gerenciamento de Residuos Solidos em 2025
**Brief**: pgrs empresa como fazer (pilar, cluster pgrs, 4.500-5.000 palavras)
**Data**: 2026-04-02

**Resultado**: 15/15 PASS | 0/15 FAIL | 0/15 WARNING

**Status geral**: APROVADO (15/15 PASS apos correcoes aplicadas pelo Auditor)

**Correcoes aplicadas diretamente pelo Auditor** (4 itens):
1. **Title tag**: Reescrito de 80 chars para 58 chars, com keyword "PGRS Empresa: Como Fazer" nos primeiros 24 chars
2. **H1**: Reescrito para incluir "Como Fazer" — de "PGRS 2025: Guia Completo do Plano de Gerenciamento de Residuos Solidos para Empresas" para "PGRS Empresa: Como Fazer o Plano de Gerenciamento de Residuos Solidos em 2025"
3. **Meta description**: Reescrita de 163 chars para 121 chars, com keyword exata "PGRS empresa como fazer" no inicio
4. **AnswerBlock H2-10**: Adicionado AnswerBlock de ~49 palavras sob "Perguntas frequentes sobre PGRS" (unico H2 que nao tinha)

**Fails criticos**: Nenhum (todos corrigidos)

**Warnings**: Nenhum

**Proxima acao**: PUBLICAR
