# Modelagem Preditiva de Consumo de Energia 
Este projeto propõe a criação e implementação de um modelo preditivo robusto para prever o consumo de energia na fábrica da FCA Fiat Chrysler Automóveis em Betim, Brasil, utilizando práticas de MLOps (Machine Learning Operations) para garantir a eficiência, escalabilidade e manutenção contínua do modelo.

## Solução
O modelo, alimentado por algoritmos de aprendizado de máquina, prevê o consumo de energia para as próximas 24 horas, permitindo ajustes operacionais proativos para reduzir custos com energia.


## Dados

- Colunas: Data, Consumo em MWh, Temperatura média

Exemplo do dataset final:

| data      | hora | consumo | temp |
|-----------|------|------------|------|
| 2023-07-01| 0    | 0.158728   | 17.1 |
| 2023-07-01| 1    | 0.000000   | 15.1 |
| 2023-07-01| 2    | 0.041606   | 14.3 |
| 2023-07-01| 3    | 0.099226   | 16.5 |
| 2023-07-01| 4    | 0.404816   | 17.7 |

### Histórico de Consumo de Energia

A Câmara de Comercialização de Energia Elétrica (CCEE) que fornece um relatório mensal com os dados de consumo em base horária para milhares de empresas de todos Brasil. A frequência de atualização da base horária de consumo tem um delay de até 4 meses. Para uma aplicação real é necessário que a empresa utilize medidores de energia inteligentes para a coleta de dados.

- Fonte: [CCEE](https://www.ccee.org.br/en/web/guest/dados-e-analises/consumo)
- Período: 2021/03 - 2023/08
- Frequência: Horária
- Formato: CSVs Diário (~7GB cada)
- Processamento: Local, usando Python e SQL

O arquivo é disponibilizado no formato .csv para cada mês, com um tamanho de em torno de 7GB. Vamos utilizar python para extrair os arquivos e SQL para extrair as tabelas de interesse.

### Dados Climáticos
Coletamos dados de temperatura do Banco de Dados Meteorológicos do INMET baseado na estação mais próxima da região em que a empresa se localiza. Para uma aplicação em tempo real o ideal é utilizar uma API que forneça dados correntes e históricos de temperatura prevista, pois os valores correntes não estarão disponíveis no momento de treino do modelo.

- Fonte: [INMET](https://tempo.inmet.gov.br)

## Como Contribuir
1. Faça um fork do repositório.
2. Faça suas alterações.
3. Envie um PR.
