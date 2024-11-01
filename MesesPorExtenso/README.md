Tive um desafio de retornar por extenso os meses que faziam parte de um intervalo de datas, para ser mais específico, data de abertura e fechamento de determinada ação

Meu contexto era as duas primeiras colunas da tabela abaixo e minha meta era retornar na terceira coluna para poder realizar um filtro bem bacana no dashboard


|dataInicio|dataFim|Meses
|--|------------|------
|20/01/2024|15/02/2024|janeiro,feveireiro
|31/01/2024|06/03/2024|janeiro,fevereiro,março
17/01/2024|14/10/2024| janeiro,fevereiro,março,abril,maio,junho,julho,agosto,setembro,outubro


Encontrei uma solução para realizar essa proeza neste link do Reddit: https://www.reddit.com/r/excel/comments/oz3lis/how_to_get_the_names_of_months_in_between_two/

Contudo, como está em inglês e senti falta de algo em Português, irei desmembrar e adicionar a fórmula aqui para a posteridade

#### Utilizei esta fórmula : 

```
=UNIRTEXTO(",";VERDADEIRO;ÚNICO(TEXTO(SEQUÊNCIA(T19-S19+1;;S19);"mmmm")))

```
#### Detalhamento da fórmula:

Seguindo pela ordem de execução da fórmula. Na parte 1  é realizado uma subtração entre a dataFim-dataInicio +1 em *T19-S19+1*  pois o resultado desta formula pode começar em 0, mas para parametros não comptacionais, mês 0 não existe, por isso se faz necessário adicionar o +1, para a visualização fazer mais sentido. 

Após isso é utilizada a fórmula SEQUÊNCIA, que com os atributos da subtração passada, irá retornar a sequência de números iniciando da data Inicial (na formula representada como S19), conforme ilustrado na imagem na Parte 1

Na parte dois, utiliza-se a função TEXTO, e o atributo "mmmm" para retornar o mês de cada data listada no passo anterior. O resultado desta formula está descrito na imagem na Parte 2

Então, utiliza-se a função único para obter apenas os valores únicos de meses apresentados na parte anterior. 

Por fim, é utilizada a função UNIRTEXTO que fará a união dos valores únicos encontrados no passo anterior e informará ele separados por vírgulas pois a mesma foi passada como parametro de delimitador na fórmula

![image](https://github.com/user-attachments/assets/38faa6cb-3d89-4a94-811d-4cff0f61014a)

