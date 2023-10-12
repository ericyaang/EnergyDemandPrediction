# Previsão de Demanda de Energia

## Motivação
Estudo de caso para aplicação dos conceitos de MLOps pelo nosso grupo de leitura.

## Limitações
Por conta de limitações técnicas,. não podemos agregar e processar dados em tempo real. Por conta disso, as previsões serão e modo batch.

## Solução
Previsão de demanda de energia à qualquer granularidade. Oferecendo uma plataforma de MLOps que permite criar, experimentar e monitorar previsões de séries temporais de demanda de energia  para múltiplos clientes.

## Tecnologias
- Language: Python, SQL
- Extraction and transformation: Jupyter Notebook, Google BigQuery
- Storage:
- Orchestration:
- Dashboard:

## Dados

- Colunas: Data, Consumo em MWh, Temperatura média

Exemplo do dataset requerido:

| Date      | Hour | Consumption | Temp |
|-----------|------|------------|------|
| 2023-07-01| 0    | 0.158728   | 17.1 |
| 2023-07-01| 1    | 0.000000   | 15.1 |
| 2023-07-01| 2    | 0.041606   | 14.3 |
| 2023-07-01| 3    | 0.099226   | 16.5 |
| 2023-07-01| 4    | 0.404816   | 17.7 |

### Histórico de Consumo de Energia

A Câmara de Comercialização de Energia Elétrica (CCEE) que fornece um relatório mensal com os dados de consumo em base horária para milhares de empresas de todos Brasil. A frequência de atualização da base horária de consumo tem um delay de até 4 meses. Para uma aplicação real é necessário que a empresa utilize medidores de energia inteligentes para a coleta de dados.

- Fonte: [CCEE](https://www.ccee.org.br/en/web/guest/dados-e-analises/consumo)
- Período: 1 ano
- Frequência: Horária
- Formato: CSVs Diário (~7GB cada)
- Processamento: Local, usando Python e SQL

O arquivo é disponibilizado no formato .csv para cada mês, com um tamanho de em torno de 7GB. Portanto, é preciso distribuir o processamento para não sobrecarregar a memória. Vamos utilizar python para extrair os arquivos e SQL para extrair as tabelas de interesse.

### Dados Climáticos
Coletamos dados de temperatura do Banco de Dados Meteorológicos do INMET baseado na estação mais próxima da região em que a empresa se localiza. Para uma aplicação em tempo real o ideal é utilizar uma API que forneça dados correntes e históricos de temperatura prevista, pois os valores correntes não estarão disponíveis no momento de treino do modelo.

- Fonte: [INMET](https://tempo.inmet.gov.br)

## Empresa Alvo
- A definir


## Como Contribuir
1. Faça um fork do repositório.
2. Faça suas alterações.
3. Envie um PR.

