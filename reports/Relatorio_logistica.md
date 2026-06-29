# Relatório de Insights: Otimização Logística e Análise Preditiva

## 1. Resumo dos Principais Achados
A análise exploratória e a modelagem preditiva dos dados da Olist permitiram identificar os seguintes pontos críticos:
* **Previsibilidade de Performance**: O modelo Random Forest obteve um AUC de 0.91, confirmando a alta capacidade de antecipar atrasos antes da efetivação da entrega.
* **Dominância do Tempo de Trânsito**: Identificou-se que a variável `tempo_entrega_dias` é o preditor quase absoluto de atrasos, com uma importância de 0.9944 no modelo.
* **Resiliência Climática**: Ao contrário da hipótese inicial, a correlação entre pluviosidade (`media_chuva_mm`) e atrasos foi mínima (0.07), indicando que o clima não é um gargalo operacional significativo na escala observada.

## 2. Discussão e Relevância para a Problemática
A problemática abordada focava na identificação de causas raízes para a quebra de SLA (Service Level Agreement). 
* A descoberta de que o tempo de trânsito é o vetor principal de risco retira a responsabilidade de fatores externos imprevisíveis (como o clima) e a coloca sobre o controle dos processos internos de logística.
* A alta precisão do modelo (AUC 0.91) é relevante pois permite que a gestão logística pare de atuar de forma reativa, passando a antecipar problemas através de dados.

## 3. Sugestões de Ações e Soluções
Com base nos insights obtidos, recomenda-se a implementação das seguintes estratégias:
* **Sistema de Alerta Precoce (Early Warning)**: Utilizar o modelo preditivo para classificar pedidos em risco (target=1) no momento do despacho.
* **Priorização Logística**: Pedidos sinalizados com alta probabilidade de atraso devem ser alocados para modalidades de transporte mais rápidas ou receber monitoramento dedicado.
* **Revisão de Prazos de SLA**: Ajustar os prazos de entrega prometidos aos clientes em rotas específicas onde os dados confirmam que o tempo médio de trânsito excede o limite estipulado, reduzindo a incidência de atrasos por design.
* **Integração Visual**: Utilizar o dashboard desenvolvido no Looker Studio como a ferramenta central de monitoramento para a equipe de operações.
*
