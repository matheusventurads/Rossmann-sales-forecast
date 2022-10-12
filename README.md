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
