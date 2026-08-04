# 🧪 Entrega do Projeto: Engenharia de Dados & Análise Exploratória (EDA)


[![Status](https://img.shields.io/badge/STATUS-CONCLU%C3%8DDO-green)](#)
[![Nível](https://img.shields.io/badge/N%C3%8DVEL-JUNIOR-blue)](#)

Este projeto tem como objetivo principal a construção de um pipeline de dados robusto, integrando bases transacionais de entrega (Olist), dados geográficos (OpenStreetMap) e dados meteorológicos (INMET), envolvendo uma análise de gargalos logísticos e o impacto de fatores externos no tempo de entrega.

---

## 🚀 Tecnologias Utilizadas
* **Linguagem:** Python 3.12
* **Processamento Distribuído:** Apache PySpark
* **Manipulação de Dados:** Pandas, NumPy
* **Engenharia Geoespacial:** OSMnx, NetworkX, GeoPandas
* **Visualização de Dados:** Looker Studio
* **Infraestrutura:** Google Colab, Google Drive (Data Lake)

---

🛠️ Etapas do Pipeline

O fluxo de processamento é organizado em cinco etapas principais:

### 1. Configuração e Ingestão Inicial
* Configuração do ambiente PySpark com otimização de memória.
* Leitura e conversão de datasets originais (CSV) para o formato Parquet, ocorrendo maior eficiência de I/O e atualizações.
* Tratamento inicial de tipos e limpeza de CEPs para garantir integridade nas junções.

### 2. Tratamento de Pedidos (Olist)
* Consolidação das tabelas transacionais (`orders`, `customers`, `items`, `reviews`, `geolocation`).
* Aplicação de técnicas de *broadcast join* para otimização de desempenho no cluster Spark.
* Criação de métricas de negócio, como `dias_atraso` e identificação de `is_gargalo` (atrasos).

### 3. Integração Meteorológica (INMET)
* Ingestão de dados históricos climáticos.
* Limpeza e normalização de variáveis como `media_chuva_mm` e `max_chuva_mm`.
* Cruzamento de dados meteorológicos com dados reais de entrega para análise de impacto climático.

### 4. Malha Rodoviária (OpenStreetMap)
* Processamento de gráficos de estradas.
* Cálculo de métricas de trafegabilidade (`speed_kph`, `travel_time`).
* Particionamento estratégico dos dados por `estado` para acelerar consultas futuras.

### 5. Data Mart e Análise (EDA)
* Criação do *Data Mart* consolidado (`df_finallookker_dashboard.parquet`).
* Análise de brilho entre pluviosidade, frete, localização e o *alvo* (atraso na entrega).
* Geração de mapas de calor para visualização de padrões estatísticos.

---

📊 Dashboard Interativo (Looker Studio)

O projeto conta com um painel interativo de 3 páginas estruturado para análise executiva:
1. **Visão Geral Logística:** Acompanhamento de KPIs globais e evolução temporal de entregas.
2. **Análise de Causa Raiz:** Cruzamento entre fatores climáticos vs. gargalos de tráfego urbano.
3. **Matriz de Soluções e Impacto:** Segmentação por faixas de atraso e ações operacionais (*Last Mile*).
   
<img width="837" height="612" alt="visao_geral_looker" src="https://github.com/user-attachments/assets/c69d3c45-7657-43cc-9b3e-e88497c3213f" />
<img width="827" height="615" alt="pagina2_looker" src="https://github.com/user-attachments/assets/1de5bfff-0679-4fa9-b7ee-fa2e18be232c" />
<img width="827" height="613" alt="pagina3_looker" src="https://github.com/user-attachments/assets/cc891f7a-c7a1-4ebd-bf57-11763d3afa0f" />



---

📊 Principais Resultados da Auditoria

* **Volumetria:** O processamento final consolidou 99.441 registros de pedidos.
* **Qualidade:** Implementação de filtros rigorosos para remover nulos e inconsistências, resultando em uma base refinada pronta para dashboards no Looker Studio.
* **Desempenho:** Uso de `repartition` e `partitionBy` para atualização e otimização da persistência dos dados.

---



