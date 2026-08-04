# Projeto: Otimização de Logística e Inteligência de Dados

## 1. Definição do Problema e Justificativa

O setor logístico enfrenta desafios críticos na manutenção dos níveis de serviço (SLA), onde a incapacidade de antecipar gargalos operacionais e viários impacta diretamente a satisfação do cliente (`review_score`) e a eficiência das entregas.

Este projeto justifica-se pela necessidade de transformar dados brutos de pedidos, geolocalização e condições meteorológicas em inteligência estratégica. A análise preditiva revelou que as intempéries climáticas não são o fator primário de atraso, direcionando o foco do projeto para a mitigação de gargalos de tráfego urbano e otimização da etapa final de entrega (*Last Mile*).

---

## 2. Estratégia de Operação

Para mitigar os impactos identificados, o projeto propõe ações estratégicas baseadas na análise de dados:

* **Roteirização Inteligente Dinâmica:** Integração de inteligência geográfica para recalcular rotas em tempo real, contornando picos de trânsito em zonas urbanas de alta densidade.
* **Redimensionamento da Malha (Micro-Hubs):** Descentralização da distribuição por meio de pontos de apoio locais nas cidades que registram os maiores prazos de atraso.
* **Flexibilização de Janelas de Entrega:** Reajuste dinâmico nos Prazos Estimados de Entrega (ETA) em horários de pico, preservando a experiência do cliente e a avaliação do serviço.

---

## 3. Arquitetura de Visualização de Dados (Looker Studio)

O projeto culmina em um painel interativo estruturado em 3 páginas estratégicas para tomada de decisão executiva:

* **Página 1 - Visão Geral Logística:** Monitoramento de KPIs globais (Volume de Pedidos, Faturamento de Frete, Média de Atrasos e Satisfação).
* **Página 2 - Análise de Causa Raiz:** Correlação espacial e climática demonstrando o impacto do tráfego urbano vs. fatores meteorológicos na performance de entrega.
* **Página 3 - Matriz de Soluções e Impacto:** Segmentação por faixas de atraso, estimativa do faturamento retido e direcionamento de planos de ação operacionais.
*
