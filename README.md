# 🎮 Xbox Game Pass — Sales Dashboard - Desafio DIO

> Dashboard de vendas interativo construído no Excel, com foco na análise de assinaturas, receita e comportamento dos assinantes do Xbox Game Pass ao longo de 2024.

---

## 📊 Sobre o Projeto

Este projeto foi desenvolvido como parte de um desafio de análise de dados com foco em **visualização e organização de informações de vendas**. O objetivo foi transformar dados brutos de assinantes em um painel visual claro, funcional e com identidade visual alinhada ao Xbox (tema escuro + verde).

O dashboard permite uma leitura rápida do desempenho de vendas e serve como base para tomada de decisões estratégicas.

---

## 📁 Dados Utilizados

| Campo | Descrição |
|---|---|
| `Subscriber ID` | Identificador único do assinante |
| `Name` | Nome do assinante |
| `Plan` | Plano escolhido (Core, Standard, Ultimate) |
| `Start Date` | Data de início da assinatura |
| `Auto Renewal` | Se possui renovação automática (Yes/No) |
| `Subscription Price` | Preço base da assinatura |
| `Subscription Type` | Tipo de ciclo (Monthly, Quarterly, Annual) |
| `EA Play Season Pass` | Se possui o add-on EA Play |
| `Minecraft Season Pass` | Se possui o add-on Minecraft |
| `Coupon Value` | Valor de desconto aplicado |
| `Total Value` | Valor total pago pelo assinante |

**Total de registros:** 295 assinantes | **Período:** Janeiro a Dezembro de 2024

---

## 🛠️ Passo a Passo — Como o Dashboard foi Construído

### 1. Leitura e Entendimento dos Dados
- A aba **`Bases`** contém a base bruta com 295 assinantes e 13 colunas
- Os dados cobrem todo o ano de 2024 (Jan–Dez)
- Foram identificadas as dimensões de análise: plano, tipo de assinatura, renovação automática, add-ons e evolução temporal

### 2. Criação das Tabelas de Apoio (aba `Cálculos`)
- Foram criadas tabelas-pivot usando fórmulas Excel (`SUMIF`, `COUNTIF`, `COUNTIFS`, `SUMPRODUCT`) para não alterar a base original
- **Tabela 1:** Receita e quantidade por Plano (Core / Standard / Ultimate)
- **Tabela 2:** Receita e quantidade por Tipo de Assinatura (Mensal / Trimestral / Anual)
- **Tabela 3:** Quantidade com e sem Renovação Automática
- **Tabela 4:** Novos assinantes por mês (Jan–Dez), usando `COUNTIFS` com `DATE()`
- **Tabela 5:** Assinantes com add-ons EA Play e Minecraft

### 3. Construção do Dashboard (aba `Dashboard`)
- Fundo escuro (`#0F0F0F`) com cards em azul-escuro (`#16213E`) para contraste
- **Barra de título** com identidade Xbox: ícone ⬛ + texto em verde `#22C55E`
- **Linha separadora verde** `#107C10` logo abaixo do título

### 4. KPI Cards (Indicadores Principais)
Cinco cards de destaque com fórmulas dinâmicas:

| KPI | Fórmula |
|---|---|
| Total de Assinantes | `=COUNTA(Bases!A2:A296)` |
| Receita Total (R$) | `=SUM(Bases!M2:M296)` |
| Plano Ultimate | `=COUNTIF(Bases!C2:C296,"Ultimate")` |
| Assinatura Mensal | `=COUNTIF(Bases!G2:G296,"Monthly")` |
| Renovação Auto. | `=COUNTIF(Bases!E2:E296,"Yes")` |

### 5. Gráficos Inseridos
Foram criados **6 gráficos** conectados diretamente às tabelas da aba `Cálculos`:

| Gráfico | Tipo | O que mostra |
|---|---|---|
| Receita por Plano | Colunas | Qual plano gera mais receita |
| Assinantes por Plano | Colunas | Distribuição de assinantes por plano |
| Receita por Tipo de Assinatura | Pizza | Share de receita: Mensal, Trimestral, Anual |
| Novos Assinantes por Mês | Linha | Evolução de aquisições ao longo do ano |
| Assinantes com Add-ons | Barras Horizontais | Comparativo EA Play vs. Minecraft |
| Renovação Automática | Pizza | % de assinantes com e sem renovação ativa |

### 6. Estética e Tema Xbox
- Paleta de cores: `#107C10` (verde Xbox), `#22C55E`, `#2AE6B1`, `#9BC848`
- Fonte padrão: **Arial** em todo o arquivo
- Aba do Dashboard destacada com cor verde no Excel
- Grid desabilitado na aba Dashboard para leitura mais limpa

---

## ✅ Resultado Final

| Indicador | Valor |
|---|---|
| Total de Assinantes | **295** |
| Receita Total | **R$ 7.633** |
| Plano mais popular | **Core** (101 assinantes) |
| Maior receita | **Plano Ultimate** (R$ 5.388) |
| Tipo de assinatura líder | **Mensal** (139 assinantes) |
| Add-on mais popular | **Minecraft** (194 assinantes) |

---

## 🗂️ Estrutura do Arquivo

```
xbox_dashboard.xlsx
├── Assets       → Paleta de cores e ícones de referência
├── Bases        → Dados brutos dos 295 assinantes
├── Cálculos     → Tabelas de apoio com fórmulas para os gráficos
└── Dashboard    → Painel visual final com KPIs e gráficos
```

---

## 🚀 Como Reproduzir

1. Faça o download do arquivo `xbox_dashboard.xlsx`
2. Abra no **Microsoft Excel** (versão 2016 ou superior) ou **LibreOffice Calc**
3. Habilite o conteúdo/macros se solicitado
4. Navegue até a aba **`Dashboard`** para visualizar o painel completo
5. Os gráficos e KPIs atualizam automaticamente caso os dados da aba `Bases` sejam modificados

---

## 🛠️ Ferramentas Utilizadas

- **Microsoft Excel** — Criação do dashboard, gráficos e fórmulas
- **Python + openpyxl** — Automação da construção do arquivo
- **pandas** — Análise exploratória dos dados

---

## 👤 Tiago A R Resende.
---

<div align="center">

Se esse projeto te ajudou de alguma forma, deixa uma ⭐ no repositório!

</div>

