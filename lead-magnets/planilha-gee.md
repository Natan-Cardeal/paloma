# Planilha de Inventario de Emissoes GEE Simplificado

> **Paloma** | paloma.eco.br
> Material educacional gratuito — versao 1.0, abril 2026

---

## O que e esta planilha

Este documento acompanha a planilha modelo (Google Sheets/Excel) que voce acabou de baixar. Aqui voce encontra instrucoes detalhadas para preencher cada aba e calcular as emissoes de **gases de efeito estufa (GEE)** da sua empresa em **tCO2e/ano** (toneladas de CO2 equivalente por ano).

A metodologia segue o **GHG Protocol** (Protocolo de Gases de Efeito Estufa), padrao global desenvolvido pelo WRI e WBCSD, adaptado com fatores de emissao brasileiros publicados pelo **MCTI** (Ministerio da Ciencia, Tecnologia e Inovacao).

---

## Estrutura da Planilha

A planilha tem cinco abas. Preencha na ordem indicada.

---

### Tab 1 — Dados da Empresa

**Objetivo:** Identificar a empresa e o periodo reportado.

Campos para preenchimento:

- **Razao social**
- **CNPJ**
- **Setor de atividade** (CNAE principal)
- **Endereco da unidade reportada**
- **Periodo do inventario** (ex: janeiro a dezembro de 2025)
- **Responsavel pelo preenchimento** (nome e cargo)
- **Numero de funcionarios**
- **Area construida (m2)**
- **Faturamento anual (R$)** — opcional, usado para calcular intensidade de emissoes

Esses dados aparecem no cabecalho do resultado consolidado e sao essenciais se voce quiser incorporar o inventario em um Relatorio de Sustentabilidade.

---

### Tab 2 — Escopo 1: Combustiveis (Emissoes Diretas)

**Objetivo:** Calcular emissoes de combustiveis queimados diretamente pela empresa.

O **Escopo 1** cobre fontes de emissao que a empresa controla diretamente: veiculos proprios, geradores, caldeiras, fornos e processos industriais.

| Combustivel | Unidade | Fator de Emissao (kgCO2e/unidade) | Fonte |
|---|---|---|---|
| Diesel | litro | 2,6030 | MCTI, 2024 |
| Gasolina comum | litro | 2,2120 | MCTI, 2024 |
| GLP (gas de cozinha) | kg | 2,9370 | MCTI, 2024 |
| Gas natural | m3 | 2,1480 | MCTI, 2024 |
| Etanol | litro | 0,0000 (biogenico) | MCTI, 2024 |

**Como preencher:**

1. Na coluna "Consumo anual", insira o volume total consumido no periodo
2. A planilha multiplica automaticamente pelo fator de emissao
3. O resultado aparece em kgCO2e — a planilha converte para tCO2e (divide por 1.000)

**Dica:** Levante o consumo a partir de notas fiscais de compra de combustivel, registros de abastecimento da frota ou faturas do fornecedor de gas.

**Nota sobre etanol:** Emissoes de queima de etanol sao classificadas como biogenicas (carbono absorvido durante o crescimento da cana). Por convencao do GHG Protocol, sao reportadas separadamente e nao somam ao total.

---

### Tab 3 — Escopo 2: Eletricidade (Emissoes Indiretas por Energia)

**Objetivo:** Calcular emissoes da energia eletrica consumida.

O **Escopo 2** cobre emissoes indiretas associadas a compra de eletricidade. No Brasil, o fator de emissao varia conforme a matriz energetica do **SIN** (Sistema Interligado Nacional).

| Parametro | Valor | Fonte |
|---|---|---|
| Fator de emissao medio SIN | 0,0480 tCO2e/MWh | MCTI, 2024 (grid medio) |

**Como preencher:**

1. Reuna as 12 faturas de energia eletrica do periodo
2. Some o consumo total em **kWh**
3. Insira o valor total na celula indicada
4. A planilha converte kWh para MWh (divide por 1.000) e aplica o fator SIN

**Dica:** Se sua empresa tem mais de uma unidade, some os consumos ou crie uma linha por unidade. Se voce compra energia no mercado livre com certificados de energia renovavel (I-REC), registre separadamente — as emissoes podem ser zero no Escopo 2.

---

### Tab 4 — Escopo 3: Emissoes Indiretas Simplificado

**Objetivo:** Estimar emissoes de fontes que a empresa nao controla diretamente.

O **Escopo 3** e o mais complexo e abrangente. Nesta versao simplificada, cobrimos apenas duas categorias relevantes para a maioria das PMEs:

**Categoria 6 — Viagens aereas corporativas**

| Tipo de voo | Fator de Emissao | Fonte |
|---|---|---|
| Domestico (< 1.000 km) | 0,133 kgCO2e/passageiro-km | DEFRA, 2024 |
| Domestico (> 1.000 km) | 0,102 kgCO2e/passageiro-km | DEFRA, 2024 |
| Internacional | 0,089 kgCO2e/passageiro-km | DEFRA, 2024 |

**Como preencher:** Liste cada trecho voado, a distancia aproximada e o numero de passageiros. A planilha calcula automaticamente. Use ferramentas online de distancia entre aeroportos se necessario.

**Categoria 4 — Transporte terceirizado (upstream)**

| Tipo | Fator de Emissao | Fonte |
|---|---|---|
| Caminhao medio (diesel) | 0,062 kgCO2e/t-km | MCTI, 2024 |

**Como preencher:** Estime o peso transportado (toneladas) e a distancia media (km) para seus principais fornecedores ou centros de distribuicao.

---

### Tab 5 — Resultado Consolidado

**Objetivo:** Apresentar o total de emissoes da empresa.

Esta aba e preenchida automaticamente com base nas Tabs 2, 3 e 4. Ela mostra:

- **Emissoes por escopo** (tCO2e/ano)
  - Escopo 1: _____ tCO2e
  - Escopo 2: _____ tCO2e
  - Escopo 3: _____ tCO2e
- **Total**: _____ tCO2e/ano
- **Emissoes biogenicas** (reportadas separadamente): _____ tCO2e
- **Intensidade de emissoes**:
  - Por funcionario: _____ tCO2e/funcionario
  - Por faturamento: _____ tCO2e/R$ milhao (se informado na Tab 1)
  - Por area: _____ tCO2e/m2

O grafico de pizza mostra a participacao de cada escopo no total. Use esses dados para identificar onde estao as maiores oportunidades de reducao.

---

## Limitacoes desta planilha

- Os fatores de emissao sao aproximacoes nacionais. Setores especificos podem ter fatores mais precisos.
- O Escopo 3 simplificado cobre apenas duas categorias. Um inventario completo inclui ate 15 categorias (compras, residuos, deslocamento de funcionarios, etc.).
- Esta planilha nao substitui um inventario auditado por terceira parte.
- Para fins de reporte ao **Programa Brasileiro GHG Protocol** ou ao **CDP**, e necessario metodologia completa e verificacao externa.

---

## Inclua esses dados no seu Relatorio de Sustentabilidade profissional

Se voce ja preencheu esta planilha, voce tem os dados ambientais basicos que compoe a secao de emissoes de um Relatorio de Sustentabilidade. A Paloma incorpora seus dados de inventario GEE diretamente no relatorio, sem custo adicional.

Conheca os planos: **paloma.eco.br/precos**

---

*Fatores de emissao baseados em publicacoes do MCTI (2024) e DEFRA (2024). Verifique atualizacoes anuais antes de usar para reporte oficial. Este material tem carater educacional.*

*Paloma — Sustentabilidade acessivel para PMEs brasileiras.*
