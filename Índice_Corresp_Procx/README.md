Oi, oii eu do futuro e demais entusiastas e curiosos kkkkk, neste repositório estão alguns conteúdos que me ajudaram a mergulhar nestas principais fórmulas:

- https://www.guiadoexcel.com.br/como-retornar-o-mes-da-maior-e-da-menor-venda-no-excel/ : e foi aqui que comecei e entendi grande parte como deveria realizar a lógica da fórmula 

- https://www.youtube.com/watch?v=9nt6N0wfP2A: aqui já fui para um viés de tentar utilizar outra função de procura e em partes deu bom, mas ainda faltava refinar e não fiquei satisfeita com a solução de concatenar as coisas. Okay, achei bem válido, mas estava disposta a procurar um pouco mais

- https://www.escoladnc.com.br/blog/funcao-procx/: aqui apenas para dar uma visão geral do procx

- https://www.youtube.com/watch?v=57Gxo0cAxe8: aqui fui muito feliz, pois estava chegando perto, mas ainda faltava tempero, no meu caso pelo que me lembro varíavel. Pois no video mostra a busca de duas apenas e uma busca horizontal, e, eu estava em uma busca dupla, tanto horizontal como vertical, horizontal para descobrir a linha onde esta a cliente e o produto e vertical para descobrir o mês que mais vendeu aquele determinado produto de determinado cliente. Spoiler do fuuro, não consegui alinhar as duas :/, mas vida que segue 

- https://exceldoseujeito.com.br/aprenda-a-usar-procv-para-pesquisar-na-planilha/ : aqui foi bacana para entender o melhor um pouco mais do procv e a parte so SomaSe foi bastante intessante também

- https://exceldoseujeito.com.br/como-solucionar-problemas-de-erros-parte-1-nd/: Achei incrível esse post sobre erros, esse de ND estava dando várias vezes durante as análises e foi bem bom ter um guia mais explicatico do que ele representa

- https://www.youtube.com/watch?v=8XdMFGmHmyA: Aqui encontrei o ouro da multiplicação entre as colunas para encontrar o valor 1 onde os valores coincidirem, recomendo demais.

- https://exceleasy.com.br/procx-no-excel/: Aqui foi o diamente, muitos exemplos de Procx, gostei bastante da forma aninhada e recomendo demais a leitura. Também tem um breve guia de erros, mas é uma leitura bem válida

E abaixo, comentários que julguei importante:

- o PROCX realiza buscas horizontais ou verticais, mas não as duas na mesma análise. Ao menos eu não consegui implmentar e em partes entendi. 
- Para encontrar um valor que tenha várias dimensões, se caso precisar no futuro, é interessante realizar uma multiplicação para tentar encontrar a única referência entre os 3 que resulte no valor 1. Como por exemplo:

``` =Planilha1!A2='Clientes2023'!A2:A138437)*Planilha1!D2='Clientes2023'!H2:H138437)*Planilha1!E2='Clientes2023'!I2:T138437) ```

  * Apenas para fins de relembrar, os dados na Planilha1, nas colunas respectivamente, são: código do Cliente, descrição do Produto e Maior valor de Venda do Produto. 





