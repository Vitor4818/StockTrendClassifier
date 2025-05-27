# 📈 Classificador de Tendências de Ações

Este projeto apresenta uma análise completa e classificação do comportamento de ações utilizando dados históricos do índice S&P 500. O principal objetivo foi identificar padrões e entender as variáveis que mais influenciam os retornos dos ativos, por meio de um fluxo de trabalho estruturado de ciência de dados — desde a limpeza dos dados até a modelagem preditiva.

---

## 🧠  Resumo do Projeto

O estudo foi conduzido com dados históricos do S&P 500, com o propósito de identificar os fatores chave que impactam os retornos das ações. Para isso, explorei um pipeline completo:

- 📥 Análise Exploratória de Dados
- 🧼 Limpeza dos Dados
- 🔧 Engenharia de Atributos (Feature Engineering)
- 📊 Análise Visual
- 🌀 Agrupamento (Clustering)
- 🤖 Modelagem Preditiva

---

## ⚙️ Fluxo técnico

### 📉 Tratamento de Dados Faltantes

Foi aplicada interpolação linear nas colunas relacionadas a preços, garantindo a continuidade na série temporal e evitando a perda de padrões importantes que poderiam afetar o desempenho do modelo.
---

### 🛠️ Feature Engineering

Para enriquecer o conjunto de dados e aprofundar a análise, criei novas features, incluindo:
- Volatilidade diária (High - Low)
- Retorno percentual diário (Close / Open - 1)
- Médias móveis (SMA e EMA)
- Desvio padrão, RSI e volume transformado em log
- Distância do preço em relação às médias móveis
- Features temporais: ano, mês, dia da semana
- Target: retorno do próximo dia (positivo ou negativo)

---

### 📊 Visual Analysis & Insights

Utilizando gráficos de dispersão, histogramas, boxplots e mapas de calor, analisei a relação entre as features e o comportamento dos retornos futuros.

#### Key Insights:

Principais Insights:
- Ações com preços baixos e alta volatilidade tendem a apresentar retornos extremos, tanto positivos quanto negativos.
- Ações baratas e estáveis apresentaram retornos mais consistentes, sendo potenciais oportunidades de curto prazo.
- Ativos caros e estáveis tiveram retornos menores, porém mais predizíveis.

Essas descobertas ajudaram a definir a lógica de agrupamento para segmentar as ações por perfil risco-retorno.

---

### 🌀 Agrupamento com K-Means

Foi aplicado o algoritmo K-Means usando preço e volatilidade como principais eixos, resultando em 3 grupos distintos:

- Cluster 0: Baixo preço + Alta volatilidade → Retornos extremos
- Cluster 1: Baixo preço + Baixa volatilidade → Retornos consistentes
- Cluster 2: Alto preço + Baixa volatilidade → Retornos estáveis

Essa segmentação foi crucial para entender quais perfis de ativos tendem a se destacar no curto prazo.

---

### 🤖 Modelagem Preditiva com Random Forest

Um modelo de classificação foi construído usando o RandomForestClassifier para prever se o retorno da ação no próximo dia seria positivo ou negativo.

- Acurácia: 66%
- Apesar da complexidade do mercado, o modelo capturou padrões que permitiram previsões razoáveis de movimentações de curto prazo.
---
## 🔍 Técnologias usadas

- Python 3
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- Jupyter Notebook

