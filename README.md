# Rossmann Sales Forecast

## Conhecendo o negócio
Rossmann é uma das maiores redes de drogarias da Europa, operando mais de 3.000 lojas em 7 países da Europa. Com o intuito de realizar investimentos em suas lojas os gerentes foram encarregados de prever o faturamento de vendas das próximas 6 semanas.

## 1. Questão de negócio
Prever as vendas realizadas por todas as lojas nas próximas 6 semanas. Com milhares de gerentes individuamente realizando previsões baseadas em suas circunstâncias únicas, a acurácia pode variar consideravelmente.


### 1.1. Entendendo os dados
A base de dados é referente as vendas realizadas entre -----------------. As vendas das lojas são influenciadas por diversos fatores, como promoções, localização de competidores e escolas, feriados e sazonalidade.


|Atributo| Definição|
|--------|----------|
|Id| um id que representa uma loja e data no dataset|
|Store| um id único para cada loja|
|Sales| a receita em determinado dia|
|Customers| o número de clientes em determinado dia|
|Open| um indicador se a loja estava aberta: 0 = fechada, 1 = aberta|
|StateHoliday| indica um feriado estadual. Normalmente todas as lojas, com algumas exceções, estão fechadas em feriados estaduais. Todas as escolas estão fechadas em feriados públicos e fins de semana. a = public holiday, b = Easter holiday, c = Christmas, 0 = None.|
|SchoolHoliday| indica se a loja foi afetada por escolas públicas fechadas|
|StoreType| diferencia entre 4 modelos de loja: a, b, c, d|
|Assortment| descreve um nível de sortimento: a = basic, b = extra, c = extended|
|CompetitionDistance| distância em metros da loja competidora mais próxima|
|CompetitionOpenSince[Month/Year]| ano e mês aproximados da abertura do competidor mais próximo|
|Promo| indica se a loja está aplicando uma promoção no dia|
|Promo2| continuação contínua e consecutiva da promoção para algumas lojas: 0 = a loja não está participando, 1 = a loja está participando|
|Promo2Since[Year/Week]| descreve o ano e semana do calendário quando a loja começou a participar na Promo2|
|PromoInterval| descreve os intervalos consecutivos de início, nomeando os meses que a promoção recomeça. Ex.: 'Feb,May,Aug,Nov' significa que cada rodada começa em Fevereiro, Maio, Augusto, Novembro de qualquer ano para a loja|

## 2. Premissas de neǵocio
* Os valores nulos em CompetitionDistance foram substituidos por a maior distância multiplicada por 3, pois estas observações provavelmente indicam lojas à uma distância muito alta, o que significa que não há competição.
* Dias com valores de vendas zerado foram desconsiderados.
* Dias onde as lojas estavam fechadas foram desconsiderados.
* Os valores faltantes na coluna 'CompetitionOpenSince' e 'Promo2Since'foram definidos com os valores de ano e mês da coluna 'Date'.

## 3. Planejamento da solução
O planejamento foi dividido em três etapas:

### 3.1. Produto Final
O resultado entregue será um aplicativo que apresente as previsões de vendas das próximas 6 semanas, facilitando e agilizando o acesso a informação.

### 3.2. Processo
#### _Entendendo o problema de negócio_
Entender a motivação para a previsão e assim planejar a solução mais efetiva.

#### _Coleta de dados_
Coleta dos dados das lojas e vendas na plataforma [Kaggle](https://www.kaggle.com/competitions/rossmann-store-sales/data).

#### _Limpeza dos dados_
Colunas renomeadas, tipo dos dados alterados e colunas com valores nulos preenchidas.

#### _Análise Exploratória de Dados (AED)_
Exploração dos dados para entendimento de negócio e descoberta de insights para auxílio na determinação de features no treinamento do modelo de machine learning.

#### _Feature Engineering_
Criação de novas features derivadas das originais para o uso no modelo de machine learning.

#### _Preparação dos dados_
Aplicação de técnicas de normalização, rescaling e encoding dos dados, assim como transformação da variavél resposta.

#### _Feature Selection_
Seleção das features relevantes que serão utilizadas para treinamento do modelo através do algoritmo Boruta.

### _Machine Learning Modeling_
Treinamento de algoritmos de Regressão com cross-validation em Time Series. O modelo selecionado foi aperfeiçõado com Hyperparameter fine tuning.

#### _Avaliação do Modelo_
  Avaliação do modelo treinado utilizando das seguintes técnicas: MAE, MAPE, RMSE e R².

#### _Resultados Financeiros_
Tradução do resultado para valores de negócio.

#### _Deploy do Modelo (Telegram Bot)_
Implementação da API para previsão de vendas através do aplicativo Telegram.

### Ferramentas
* Python 3.8
* Pandas, Seaborn, Matplotlib e Sklearn
* Flask e Python API's
* Git e Heroku
* Boruta
* Algoritmos de Regressão (Regressão Linear/Lasso, Random Forest, XGBoost/LGBM Regressors)
* Cross-Validation, Hyperparameter Optimization
* Métricas de Performance (RMSE, MAE, MAPE, R2)

## 4. Destaque dos Insights de negócio


## 5. Modelos de Machine Learning
Foram treinados 6 modelos de machine learning para previsão das vendas, com cross-validation:
* Média (utilizado como Baseline)
* Regressão Linear
* Regressão Linear Regularizada
* Random Forest Regressor
* XGBoost Regressor
* Light GBM Regressor
