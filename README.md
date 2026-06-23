# projeto-delivery-logistic
# 🚚 Otimização de Logística e Precificação Dinâmica no Mercado de Delivery

![Status do Projeto](https://img.shields.io/badge/Status-Em%20Desenvolvimento-orange?style=for-the-badge)
![Nível](https://img.shields.io/badge/N%C3%ADvel-S%C3%AAnior-blue?style=for-the-badge)

> *Abordagem Estratégica:* Este projeto redesenha a eficiência da última milha (last-mile) integrando dados transacionais de e-commerce, malhas viárias urbanas e séries temporais meteorológicas para mitigar atrasos e prejuízos operacionais.

---

## 🎯 1. O Desafio do Negócio (Business Problem)

O crescimento acelerado do mercado de delivery e e-commerce trouxe um desafio crítico: a ineficiência na *última milha* (last-mile delivery), a etapa final e mais onerosa da entrega. Atualmente, as plataformas enfrentam dificuldades crônicas para prever o tempo exato de entrega e para calcular taxas de frete que sejam atraentes para o cliente, mas que ainda cubram os custos operacionais (combustível, manutenção e remuneração de entregadores). 

A flutuação imprevisível da demanda — influenciada por horários de pico, condições climáticas severas e trânsito — gera gargalos logísticos severos. O resultado direto desse cenário é medido em:
* 📉 *Aumento do Churn:* Cancelamentos de pedidos e perda de clientes por quebra de expectativa.
* 💸 *Erosão da Margem:* Prejuízo financeiro direto para as plataformas e lojistas parceiros devido ao frete estático deficitário.

### 💡 A Solução via Dados
A ciência de dados mitiga esse gargalo através de modelagem preditiva e otimização algorítmica. Utilizando dados históricos de entregas cruzados com variáveis externas, este projeto estrutura a base analítica para a criação de modelos de Machine Learning capazes de prever o tempo de entrega com alta precisão e implementar motores de *precificação dinâmica*, ajustando o valor do frete e o raio de atendimento em tempo real para garantir o nível de serviço (SLA) e a sustentabilidade financeira do ecossistema.

---

## 💾 2. Ecossistema de Dados (Data Sources)

O projeto simula um ambiente de Big Data real utilizando três fontes de dados públicas, complexas e anonimizadas:

*   *📦 Base 1: Olist Store E-commerce Dataset (Kaggle)*
    *   Conteúdo: Dados estruturados relacionais de mais de 100 mil pedidos reais no Brasil (2016-2018). Inclui geolocalização (coordenadas zip_code), status de entrega, preço, frete e avaliações dos clientes.
    *   Coleta: Consumo automatizado via API do Kaggle (kaggle api).
*   *🗺️ Base 2: Malha Rodoviária Urbana (OpenStreetMap)*
    *   Conteúdo: Dados geoespaciais estruturados e semiestruturados contendo rotas, restrições de tráfego, distâncias reais e pontos de interesse (POIs).
    *   Coleta: Extração automatizada em Python via biblioteca OSMnx e API Overpass.
*   *🌧️ Base 3: Histórico Meteorológico (INMET)*
    *   Conteúdo: Séries temporais horárias com registros de precipitação (chuva em mm) e temperatura nas capitais estudadas.
    *   Coleta: Integração via scripts de raspagem com requests e BeautifulSoup no portal oficial de dados abertos.

---

## 🛠️ 3. Arquitetura de Dados Multi-Ferramenta (EDA)

Uma arquitetura sênior não força todas as etapas em uma única tecnologia. Cada ferramenta foi alocada exclusivamente no seu cenário de *eficiência máxima*:

| Ferramenta | Cenário de Aplicação Exclusiva | Objetivo Técnico |
| :--- | :--- | :--- |
| ![Google Sheets](https://img.shields.io/badge/Google%20Sheets-34A853?style=flat&logo=googlesheets&logoColor=white) | Inspeção Visual Rápida | Amostragem inicial (1k linhas) para detectar anomalias óbvias e nulos antes do código. |
| ![SQL](https://img.shields.io/badge/SQL-CC292B?style=flat&logo=postgresql&logoColor=white) | Estruturação e Filtragem | Execução de queries complexas, validação de chaves (PK/FK) e remoção de incongruências temporais. |
| ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) | Tratamento Fino e Estatística | Conversão de tipos (datetime), remoção de outliers via IQR (Seaborn) e mapas de calor (GeoPandas). |
| ![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=flat&logo=apachespark&logoColor=white) | Processamento de Big Data | Processamento em memória das séries temporais massivas do INMET e grafos do OSM, evitando erros de OOM. |

---

## 📊 4. Estrutura do Relatório de Insights

Tradução direta de dados estatísticos em tomadas de decisão executiva (BI):

1.  *Data Findings (Achados):* Quantificação de minutos adicionais de atraso por mm de chuva, isolamento de gargalos viários urbanos específicos e cálculo do descolamento real de SLA.
2.  *Business Impact (Impacto):* Avaliação do impacto do atraso no Customer Lifetime Value (LTV) e diagnóstico de perda de margem por frete estático sob condições severas.
3.  *Strategic Recommendations (Soluções):* Desenho de um motor de precificação dinâmica para horários críticos e algoritmo de contração automática do raio de atendimento de parceiros em tempestades.

---

## 📈 5. Arquitetura do Dashboard (Looker Studio)

Painel executivo interativo projetado para decisões operacionais em tempo real:

[Visão Geral Logística] ──> [Filtros: Período, Região Metropolitana, Condição Climática]
│
├─► [Métricas Kpi] ───► ETA Médio, SLA Compliance (%), Taxa de Churn por Atraso
├─► [Mapas Geográficos] ► Epicentros e Densidade de Gargalos (Lat/Long)
└─► [Gráficos Correlação] Dispersão (Chuva vs Tempo), Barras Empilhadas (Satisfação vs Atraso)

---

## 📂 6. Organização do Repositório

```text
📦 projeto-delivery-logistica
 ┣ 📂 data                   # Documentação e instruções de acesso às bases brutas
 ┣ 📂 notebooks              # Engenharia de dados e EDA (Google Colab / Jupyter)
 ┣ 📂 sql                    # Repositório de queries e views de integração
 ┣ 📂 reports                # Relatório executivo de insights em PDF
 ┗ 📜 README.md              # Documentação principal do projeto
