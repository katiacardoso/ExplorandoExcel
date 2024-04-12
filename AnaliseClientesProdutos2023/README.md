--------Ainda precisa de ajustes, coloquei apenas o rascunho aqui--------

Estou meio perdida se isso aqui é um relatório de resultados ou de experimento - no sentido de mostrar como foi feito-, mas seguimos

Para fins de exemplificação, a planilha trabalhada é neste estilo

|idCLiente|Produto|JAN|FEV|...|QuantTotal
|--|------------|------|-----|-----|------|
|1|	Produto1|Valor|Valor| ...| SomaValores
|1|Produto2|Valor|Valor| ...| SomaValores
1	|Produto3|Valor|Valor| ...| SomaValores
|2|	Produto5|Valor|Valor| ...| SomaValores
|2|Produto1|Valor|Valor| ...| SomaValores
2|Produto3|Valor|Valor| ...| SomaValores
|3|	Produto10|Valor|Valor| ...| SomaValores
|3|Produto2|Valor|Valor| ...| SomaValores
3|Produto5|Valor|Valor| ...| SomaValores

Resuminho das colunas das planilhas para ficar mais facil lembrar o que a formula esta fazendo 

Principal

A: idCliente
H: descrição do produto
U: QuantTotal de vendas dos 12 meses para determinado produto de determinado cliente

Planilha1

A: idCliente
E: descriçãoProduto


Inicialmente criei uma nova planilha - chamaremos de auxiliar ou nas formulas de Planilha1 - para identificar os códigos únicos de cliente. Eu fiz com a fórmula de *único*, mas recebi uma recomendação de realizar de um outro formato também, copiar toda a coluna com o comando _Ctrl+Shift+SetaParaBaixo_ e cola nesta nova planilha -ou em algum outro local que caiba - e retira os duplicados com a própria ferramenta do excel, é bem mais fácil, mas como ainda estou com um pensando formulístico não pensei nisso antes 

e então começou a brincadeira, 

### Qual produto foi o mais vendido por determinado cliente?


R: Foi uma viagem formular esta ideia, mas pensando agora até que foi bem óbvio :/, mas vamos lá. 

1° Encontrar o maior valor de volume de venda de cada produto, fiz na planilha principal mesmo, para todas as linhas da planilha e utilizei esta formula:
```
=PROCX(MÁXIMO(SE('Principal'!A:A=Planilha1!A2;'05.12_Cliente2023'!U:U));SE('Principal'!A:A=Planilha1!A2;'Principal'!U:U);'Principal'!U:U)
```
um adendo que calculei o maior valor através de uma formula maior e está descrito com mais detalhes aqui : <https://github.com/katiacardoso/ExplorandoExcel/edit/main/Mes_MesesComMaioresQuantidades/README.md>

PROCX pois gostei bastante e segui com ele. 

2° Encontrei a descrição do produto mais vendido, atráves deste maior valor que eu tinha encontrado

```
=PROCX(D2;SE('Principal'!A:A=Planilha1!A2;'Principal'!U:U);'Principal'!H:H)
```

e foi, dai fui puxando mais perguntas:

### Qual o tipo deste produto ?

Puxei as informações de uma outra tabela que continham a mais informações do produto, e utilizei um PROCV, com a descrição que encontrei anteriormente e foi isto. Sem formula pois muitos nomes e caminhos para mudar e me perdi no caminho HA HA HA, mas assim eu consegui o tipo de produto

### Qual mês teve maior venda

Fiz um coisinha só para ele e é possível encontrar aqui: <https://github.com/katiacardoso/ExplorandoExcel/edit/main/Mes_MesesComMaioresQuantidades/README.md>

Um detalhe bastante interessante foi que consegui calcular não só o mes, mas os meses que tiveram maiores volumes de venda 

### Qual foi o desempenho de venda durante o ano?

![image](https://github.com/katiacardoso/ExplorandoExcel/assets/91233884/17f4233e-de95-4f4f-801d-bb495be06cc8)

e aqui aconteceu uma coisa interessante, observe abaixo: 

<div align="center">

![image](https://github.com/katiacardoso/ExplorandoExcel/assets/91233884/a8983b16-9ec4-47a2-a252-5e547997094f)

</div>


o 1° valor é a soma da coluna de QuantidadeTotal e o segundo e o somatorio desta conta que tinha feito acima para verificar as vendas por mês. E teve um valor de diferença, de onde será que ele saiu, ou faltou no caso né. Poderia ser uma investigação interessante. 

### 







