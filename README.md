# Projeto de Monitoramento de ações

<p align="center">
  <img src="images/analise-comparativa.png" width="45%" />
  <img src="images/analise-especifica.png" width="45%" />
</p>

Este projeto tem como objetivo a construção de um pipeline completo de dados para monitoramento de ações do mercado brasileiro, desde a ingestão via API até a visualização em dashboard interativo.

O fluxo contempla extração, transformação, armazenamento e consumo dos dados, com atualização automática diária.

<img src="images/job-atualizacao.png">

## Descrição do Projeto

Os dados são coletados via API utilizando a biblioteca yfinance, trazendo informações históricas das ações PETR4, VALE3, ITUB4, ABEV3, BBDC4, WEGE3, BBAS3.

O processamento é realizado no Databricks utilizando PySpark, realizando o tratamento de dados, padronização de colunas, conversão de tipos (datas, valores numéricos), estruturação no formato long com as colunas data, ticker e preço.

Os dados são armazenados em uma tabela no formato Delta Lake.

Foi implementado um job de atualização diária, responsável por atualizar automaticamente a tabela.

O painel foi desenvolvido no Power BI, constando na página 1 a comparação dos ativos com um gráfico de dispersão analisando risco vs retorno, gráfico de linha comparando as ações normalizada no período, e gráfico de barras exibindo o ranking de performance. Na página 2 consta a análise individual de cada ativo com os cards de preço final, preço inicial, variação percentual, mínima e máxima do período, drawdown, gráfico de linha mostrando a evolução dos preços da ação no tempo e histograma com a faixa de retorno.
