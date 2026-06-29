# 💾 Fontes de Dados
Instruções e documentação de acesso às bases brutas (Olist, OpenStreetMap e INMET).
## Fontes de Dados e Coleta

Os dados utilizados neste projeto foram integrados a partir de três bases principais:

1.  **Dados Transacionais (Olist)**: Base de pedidos e entregas contendo histórico de datas de compra, despacho e recebimento.
2.  **Dados Geográficos (OpenStreetMap)**: Utilizados para a análise da malha viária e cálculo de distância entre pontos de entrega.
3.  **Dados Meteorológicos (INMET)**: Séries históricas de pluviosidade diária, integradas ao dataset principal através da chave de data e região.

**Método de Coleta**: A ingestão dos dados foi realizada via *Data Lake* (Google Drive), utilizando o ambiente do Google Colab para processamento distribuído com PySpark.
