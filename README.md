<h2 style="text-align: left">

  [« Anterior](https://github.com/vcwild/wtp-clean) | [Apresentação](#ovr) | [Procedimento](#eda) | [Dicionário de Dados](./dicionario_dados.md) | [Próxima »](https://github.com/vcwild/wtp-model)

</h2>

## Etapas Anteriores

- [Extração de Dados](https://github.com/vcwild/wtp-extract)
- [Tratamento de Dados](https://github.com/vcwild/wtp-clean)

## Próxima Etapa

- [Modelagem de Séries Temporais](https://github.com/vcwild/wtp-model)

# Apresentação <a name="ovr"></a>

## Introdução

Análise exploratória de dados é o conjunto de métodos utilizados para identificar as características e comportamentos principais dos dados estudados, utilizando principalmente de métodos estatísticos de agregação de dados, visualização de dados e testes de validação de hipótese. 
O principal objetivo da análise exploratória é encontrar tendências, relações, padrões de comportamento, correlações, comportamentos anômalos e selecionar as melhores variáveis.

## Etapas do Projeto

- [Identificar o formato dos dados](#id)
- [Separar o conjunto de validação](#sep)
- [Definir a frequência da série histórica](#transf)
- [Selecionar as variáveis com informações relevantes](#select)
- [Agregar os dados por período](#agg)
- [Identificar e remover anomalias](#anom)
- [Imputar dados faltantes](#impute)
- [Identificar o comportamento da série temporal](#stat)


### Identificar o formato dos dados <a name="id"></a>

As variáveis de trabalho devem estar todas em formato numérico, o campo de entidade deverá ser removido da análise.

### Separar o conjunto de validação <a name="sep"></a>

O ano de 2019 não deve ser avaliado pela análise exploratória, pois será utilizado na etapa de validação do modelo de previsão.

### Definir a frequência da série histórica <a name="transf"></a>

A frequência das séries históricas devem ser identificadas e transformadas para intervalo mensal.

### Selecionar as variáveis com informações relevantes <a name="select"></a>

Deverá ser estipulado um valor mínimo de 60% de dados válidos para filtrar as séries temporais com viabilidade de modelagem. A margem de 60% será utilizada porque o conjunto de observações por variável é pequeno (< 100) e ao utilizar margens menores de valores válidos as séries receberão muitos dados imputados entre os intervalos com registro. 
Para este projeto, uma das características que define séries com percentual de válidos abaixo de 60% é a existência de um ou mais anos com registro completamente nulo. Valores abaixo serão descartados durante essa etapa, mas poderão ser utilizados futuramente mediante outros critérios.

### Agregar os dados por período anual <a name="agg"></a>

Os dados serão agregados por período anual para verificação de amplitude e comportamento ao longo do tempo, facilitando a possibilidade de encontrar tendências e outliers.

### Identificar e remover anomalias <a name="anom"></a>

Serão identificadas e removidas anomalias encontradas na série temporal, que podem ter sido oriundas de falha operacional ou eventos extremamente atípicos. Essa etapa pode ser considerada parte da modelagem de dados, porém será necessário integrá-la a análise exploratória para complementar os dados faltantes.

### Imputar dados faltantes <a name="impute"></a>

Considerando que a frequência da série será dividida mensalmente, os dados imputados serão a média ponderada entre os valores mais próximos do ponto, utilizando método euclidiano, com kNN=11.

### Identificar o comportamento da série temporal <a name="stat"></a>

Será identificado se a série possui comportamento estacionário ou não. Séries não-estacionárias deverão ser convertidas em estacionárias na fase de modelagem.

# Procedimento <a name="eda"></a>

As etapas do projeto foram realizadas passo a passo em cada uma das entidades.

- [ANAMBI](./EDA/EDA_anambi.ipynb)
- [COMPOSTAGEM](./EDA/EDA_compostagem.ipynb)
- [LEITO DE SECAGEM](./EDA/EDA_leito_de_secagem.ipynb)
- [P1](./EDA/EDA_p1.ipynb)
- [P2](./EDA/EDA_p2.ipynb)
- [P3](./EDA/EDA_p3.ipynb)
- [P4](./EDA/EDA_p4.ipynb)
- [P5](./EDA/EDA_p5.ipynb)
- [PB](./EDA/EDA_pb.ipynb)
- [PC](./EDA/EDA_pc.ipynb)
- [PD](./EDA/EDA_pd.ipynb)
- [REATOR](./EDA/EDA_reator.ipynb)

[Próxima Etapa »](https://github.com/vcwild/wtp-model)
