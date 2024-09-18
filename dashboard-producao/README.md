# Dashboard de Produção

Este repositório contém um dashboard de produção desenvolvido no Power BI. O objetivo deste dashboard é proporcionar um detalhamento mais extenso das informações de produção, facilitando a análise e a tomada de decisões com base em dados precisos e bem organizados.

### Funcionalidades do Dashboard
- **Filtro de Operador:** Permite selecionar um operador específico para visualizar informações detalhadas.
- **Filtro de Mês:** Permite selecionar um mês específico para análise detalhada.
- **Visualização Geral:** Mostra a visão geral de toda a equipe.

### Imagens de Visualização
Aqui estão algumas imagens que ilustram o dashboard:

<img src="https://github.com/jsantosi/Dashboards-PowerBi/blob/main/dashboard-producao/dashboard-producao.png">

<img src="https://github.com/jsantosi/Dashboards-PowerBi/blob/main/dashboard-producao/dashboard-producao-1.png">



## Importação e Tratamento dos Dados

### Base de Dados

- **Base Analisada:** `dashboard-producao/Produção.xlsx`
- **Relacionamento de Tabelas:** Foi feito o relacionamento entre a base de dados de produção e a tabela de operadores da empresa.
  - Arquivo de relacionamento: `dashboard-producao/operadores-da-empresa.xlsx`

### Processos Realizados

1. **Importação de Dados:** Importação de uma base de dados do Excel para o Power BI.
2. **Tratamento dos Dados:** Realização de tratamentos necessários para preparar os dados para análise.
3. **Relacionamento de Tabelas:** Relacionamento entre a base de produção e a tabela de operadores.

## Cálculos e Análises Utilizados

### Métricas Calculadas

- **Tempo de Produção:** Total de horas em que a produção está ativa.
- **Tempo de Inatividade:** Total de horas em que a produção está parada.
- **Desempenho de Produção:** Total de horas disponíveis para a produção.
- **Produção Qualificada:** Total de produtos produzidos.
- **Peças Descartadas:** Total de produtos rejeitados.
- **Índice de Qualidade:** Percentual de produtos produzidos com base no total de produtos produzidos e rejeitados.

### Fórmulas Utilizadas

  ```plaintext
  Quant. Rejeitada = SUM('BaseProdução'[Qtd Rejeitada])
  Quant. Produzida = SUM('BaseProdução'[Qtd Produzida])
  Horas = SUM('BaseProdução'[Total Horas])
  Qualidade = ([Quant. Produzida]) / ([Quant. Produzida] + [Quant. Rejeitada])
  Horas Produtivas = CALCULATE(SUM('BaseProdução'[Total Horas]), 'BaseProdução'[Ocorrência] = Blank())
  Horas Paradas = CALCULATE(SUM('BaseProdução'[Total Horas]), 'BaseProdução'[Ocorrência] <> Blank())
  Disponibilidade = ([Horas Produtivas]) / ([Horas Produtivas] + [Horas Paradas])
```






