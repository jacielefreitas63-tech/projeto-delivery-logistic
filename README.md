# 🧪 Projeto Delivery: Engenharia de Dados & Análise Exploratória (EDA)

![Status](https://img.shields.io/badge/STATUS-DESENVOLVIMENTO-brightgreen)
![Nível](https://img.shields.io/badge/NÍVEL-JUNIOR-blue)

Este projeto tem como objetivo principal a construção de um pipeline de dados robusto, integrando bases transacionais de delivery (Olist), dados geográficos (OpenStreetMap) e dados meteorológicos (INMET), visando a análise de gargalos logísticos e o impacto de fatores externos no tempo de entrega.

## 🚀 Tecnologias Utilizadas

*   **Linguagem:** Python 3.12
*   **Processamento Distribuído:** Apache PySpark
*   **Manipulação de Dados:** Pandas, NumPy
*   **Engenharia Geoespacial:** OSMnx, NetworkX, GeoPandas
*   **Infraestrutura:** Google Colab, Google Drive (Data Lake)

## 🛠️ Etapas do Pipeline

O fluxo de processamento está organizado em cinco etapas principais:

### 1. Configuração e Ingestão Inicial
*   Configuração do ambiente PySpark com otimização de memória.
*   Leitura e conversão dos datasets originais (CSV) para o formato **Parquet**, visando maior eficiência de I/O e compressão.
*   Tratamento inicial de tipos e limpeza de CEPs para garantir integridade nos *joins*.

### 2. Tratamento de Pedidos (Olist)
*   Consolidação das tabelas transacionais (`orders`, `customers`, `items`, `reviews`, `geolocation`).
*   Aplicação de técnicas de *broadcast join* para otimização de performance no cluster Spark.
*   Criação de métricas de negócio, como `dias_atraso` e identificação de `is_gargalo` (atrasos).

### 3. Integração Meteorológica (INMET)
*   Ingestão de dados históricos climáticos.
*   Limpeza e normalização de variáveis como `media_chuva_mm` e `max_chuva_mm`.
*   Cruzamento de dados meteorológicos com a data real de entrega para análise de impacto climático.

### 4. Malha Rodoviária (OpenStreetMap)
*   Processamento de grafos de estradas.
*   Cálculo de métricas de trafegabilidade (`speed_kph`, `travel_time`).
*   Particionamento estratégico dos dados por `estado` para acelerar consultas futuras.

### 5. Data Mart & Análise (EDA)
*   Criação do *Data Mart* consolidado (`df_finallookker_dashboard.parquet`).
*   Análise de correlação entre pluviosidade, frete, localização e o *target* (atraso na entrega).
*   Geração de *heatmaps* para visualização de padrões estatísticos.

## 📊 Principais Resultados da Auditoria

*   **Volumetria:** O processamento final consolidou 99.441 registros de pedidos.
*   **Qualidade:** Implementação de filtros rigorosos para remover nulos e inconsistências, resultando em uma base refinada pronta para dashboards no Looker ou ferramentas de BI.
*   **Performance:** Uso de `repartition` e `partitionBy` para otimizar a persistência dos dados.

## 💡 Como Executar
*(Adicione aqui os passos para rodar o seu código, ex: clonar o repositório, instalar requirements.txt, etc.)*
