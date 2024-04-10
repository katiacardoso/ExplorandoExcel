Tive um desafio enorme que tirei da minha cabeça para treinar. O contexto era uma planilha de vendas anuais de todos os clientes de uma empresa, seus respectivos produtos e quantidade de volume de cada mês vendido.


E eu queria responder a seguinte pergunta inicialmente: Qual o mês que vendeu em maior quantidade, o maior produto vendido por aquele determinado cliente ?

De início pode parecer até fácil, mas a minha planilha era imensa e estava com uma relação de muitos para muitos. Mais ou menos assim:


|idCLiente|Produto|JAN|FEV|
|--|------------|------|-----
|1|	Produto1|Valor|Valor
|1|Produto2|Valor|Valor
1	|Produto3|Valor|Valor
|2|	Produto5|Valor|Valor
|2|Produto1|Valor|Valor
2|Produto3|Valor|Valor
|3|	Produto10|Valor|Valor
|3|Produto2|Valor|Valor
3|Produto5|Valor|Valor

Então, para encontrar o mês que teve uma maior quantidade de volume de vendas fiz da seguinte forma:

1° Encontrei a maior quantidade vendida de todos os meses (de Jan a Dez, na tabela acima fiz apenas para demonstração) para todas as linhas. Porque um problema que estava tendo era que as informações estão verticalmente e horizontalmente. Então dessa forma eu mantive apenas no horizontal por hora. Utilizei a fórmula de maior mesmo.
```
=MAIOR(I2:T2;1)
```

2° Depois encontrei o mês que teve o maior quantidade de volume de vendas para todas as linhas da minha tabela com a fórmula abaixo:
```
=ÍNDICE($I$1:$T$1;CORRESP(W2;I2:T2;0))
```
onde, as colunas de I à T estão os meses do ano e W a coluna com a maior quantidade do volume de vendas. Para entender melhor como funciona essa formula, comentei sobre ela no repositório de Indice, Corresp e alguma coisa. 

E tá pronto o sorvetinho. Pensando assim até que foi fácil e nem quebrei cabeça para solucionar isso. Contudo, cai em um novo empasse, havia linhas em que a maior quantidade de volume de vendas era o mesmo em meses diferentes (KKKcrying), então parti em busca de uma fórmula que eu conseguisse identificar então os meses com maiores quantidades de dados. E assim foi :

```
=UNIRTEXTO(", ";VERDADEIRO; SE(I2:T2=W2; $I$1:$T$1; ""))
```

a formula de unir texto foi apenas para que o resultado fosse mostrado todo em 1 célula apenas, sem ele estavam sendo ocupadas 12. Então quebrei a cabeça para cair em um Se bem simplezinho, mas que foi bastante útil. E acabei que, consegui demonstrar também os meses que não tinham duplicidade de valores, então fica ai uma opção para calcular não apenas o mês com maior quantidade e sim os meses, como no caso desta lógica. Segue abaixo como uma amostra de como ficaram as planilhas:

|MesMaiorQuantidade|MesesMaioresQuantidades|
|--|------------|
|OUT|	OUT|
|JAN|JAN,DEZ
FEV	|FEV,JUN
MAI|MAI

