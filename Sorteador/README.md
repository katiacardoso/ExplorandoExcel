Oi, oii eu do futuro e demais entusiastas e curiosos kkkkk, neste repositório está um sorteador de nomes que é parte do conteúdo programático do curso Introduction to Data Analysis Using Excel da Rice University, o qual estou participando como ouvinte na plataforma Coursera. 

Em uma visão geral é bem simples, mas ao mesmo tempo bastante interessante.

Há esta tabela com 20 estudantes:

|Id|Student Name|
|--|------------|
|1|	Frank|
|2|Linda
3	|Angela
4|	Daniel
5|	Joshua
6	|Tammy
7	|Christine
8	|Christopher
9	|Donald
10	|Justin
11	|Earl
12	|Sean
13	|Kimberly
14|	Peter
15	|Louis
16	|Harold
17|	Anthony
18	|Lori
19	|Nicholas
20|	Fred


A ideia é criar um botão, ou um mecanismo para que quando atualizasse a tabela, realizar o sorteio de um aluno aleatoriamente. Para isto foi utilizada esta formula:

```
=PROCV(ALEATÓRIOENTRE(1;20);A2:B21;2;FALSO)
```

e para atualizar a planilha, aperte a tecla `F9`

tá pronto sorvetinho !
