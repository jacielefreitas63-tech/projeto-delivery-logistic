# Relatório de Insights: Otimização Logística e Análise Preditiva

## 1. Resumo dos Principais Achados

A análise exploratória e a modelagem preditiva dos dados de logística e entregas permitiram identificar os seguintes pontos críticos:

* **Previsibilidade de Desempenho:** O modelo *Random Forest* obteve uma métrica **AUC de 0,91**, confirmando alta capacidade para antecipar atrasos antes da efetivação do despacho da carga.
* **Dominância do Trânsito Urbano:** Identificou-se que a variável de tempo de deslocamento/trânsito é o preditor principal de atrasos, acumulando uma importância relativa de **0,9944** no modelo preditivo.
* **Resiliência Climática:** Ao contrário da hipótese inicial, a correlação entre a intensidade pluviométrica (`media_chuva_mm`) e os atrasos foi baixa (importância de **0,07**), provando que fatores meteorológicos não são os gargalos operacionais primários.

---

## 2. Discussão e Relevância para a Problemática

O problema abordado foca na identificação de causas raízes para a quebra de contrato de nível de serviço (SLA) e queda na avaliação dos clientes (`review_score`).

* **Centralidade do Tráfego Urbano:** A descoberta de que o tempo de trânsito em zonas urbanas é o vetor principal de risco retira a responsabilidade de fatores externos imprevisíveis (como chuva) e coloca o foco nos processos logísticos de *Last Mile* e malha viária.
* **Gestão Proativa baseada em Dados:** A alta precisão do modelo (AUC 0.91) permite migrar de uma gestão reativa (onde os problemas só são tratados após a reclamação do cliente) para uma atuação preventiva e automatizada.

---

## 3. Sugestões de Ações e Soluções

Com base nos insights obtidos e na modelagem preditiva, recomenda-se a implementação das seguintes estratégias:

* **Sistema de Alerta Precoce (Early Warning):** Utilização do modelo preditivo para sinalizar pedidos com alto risco de atraso (`target=1`) logo na fase de processamento do pedido.
* **Roteirização Inteligente & Dinâmica:** Integração de rotas adaptativas em tempo real para contornar gargalos de tráfego em municípios de alta densidade urbana.
* **Descentralização por Micro-Hubs (Cross-docking):** Alocação estratégica de pontos de transbordo locais nas cidades com picos históricos de atraso urbano, encurtando a última milha de entrega.
* **Revisão Dinâmica de Prazos de SLA:** Ajuste nos prazos estimados de entrega (ETA) exibidos ao cliente em rotas ou horários de pico, evitando expectativas irrealistas e preservando a satisfação do consumidor.
* **Integração Executiva via Looker Studio:** Uso do dashboard interativo de 3 páginas como painel central para acompanhamento de faturamento retido, faixas de atraso e priorização de ações corretivas.
*
