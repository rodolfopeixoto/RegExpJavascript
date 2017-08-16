# rogpe REGexp - [ Estudando REGexp ]

Desenvolvimento de um site utilizando HTML, CSS e Javascript.

Exemplo da aplicação: https://rogpe-regexp.herokuapp.com/

[www.about.me/rodolfopeixoto](http://www.about.me/rodolfopeixoto) 

Versão do Projeto 0.0.1
================

Sobre esta versão
---------------------
Site desenvolvido:
Utilizei: 
 - HTML 5
 - CSS 3
 - Javascript

Acompanhe as atualizações do projeto
---------------------



ATENÇÃO
---------------------



Configuração inicial
---------------------
Basta clonar o repositório e estudar o código, caso queira entender as técnicas.


Documentação
---------------------

Textos Test
---------------------
 ```
João Fulano,123.456.789-00,21 de Maio de 1993,(21) 3079-9987,Rua do Ouvidor,50,20040-030,Rio de Janeiro
Maria Fulana, 98765432100,11 de Abril de 1995,(11) 933339871,Rua Vergueiro,3185,04101-300,São Paulo
denise teste, 987.654.321.00,28 de Dezembro de 1991,(31)45562712,SCS Qd. 8 Bl. B-50,11,70333-900,Rio Grande
 ```

Regras de regExp
---------------------

###### Encontrar o CPF com . e - ou sem . e -.
O ponto de interrogação (?), que significa zero ou uma vez, é um quantifier. [ Se é opcional por exemplo]
```
\d{3}\.?\d{3}\.?\d{3}-?\d{2}
```
A expressão \.{0,1} diz que pode não ter o ponto, mas também pode ter um ponto só, caso tenha dois não da match
```
\d{3}\.{0,1}\d{3}\.?\d{3}-?\d{2}
```
Um conjunto de caracteres que pode ser utilizado utilizamos conchete [-.].
**OBS:** \. = ao ponto quando está na expressão, quando for utilizar dentro do [ ] utilizar [.]
```
\d{3}\.{0,1}\d{3}\.?\d{3}[-.]?\d{2}
```

Podemos mudar o \d para um intervalo, por exemplo: de 0 à 9. [0-9]
```
[0-9]{3}\.{0,1}\d{3}\.?\d{3}[-.]?\d{2}
```


Pegando por exemplo só 21 de Maio de 1993 [ Datas ]
**\s** caracter para pegar espaços em brancos. **\s{1,}** caso coloque {Número,} ele entende que é o número ou mais vezes.
outra opção é usar também o +.  {1,} = +
```
[1-3]?\d\s{1,}
```
ou
```
[1-3]?\d\s+
```

Cadeia de caracteres [A-Z] maisculo ou [a-z] minusculo, também pode-se colocar a quantidade de caracteres
[a-z]{3,5}, sendo que o número conta de 0 à n, logo se Maio = 4 caracteres e Fevereiro tem 9 caracteres, então
o mínimo é 4 - 1 = 3 e 9 - 1 = 8, sendo assim:
```
[1-3]?\d\s+de\s+[A-Z][a-z]{3,8}
```
Expressão regular final para pegar: 28 de Maio de 1991

```
[1-3]?\d\s+de\s+[A-Z][a-z]{3,8}\s+de\s\d{4}
```
Melhorando, não aceitando Anos absurdos. Sendo o primeiro [1]991 número, 1 ou 2.

```
[1-3]?\d\s+de\s+[A-Z][a-z]{3,8}\s+de\s[12]\d{3}
```
##### Quantifier
* ? - zero ou uma vez
* \* - zero ou mais vezes
* \+ - uma ou mais vezes
* {n} - exatamente n  vezes
* {n,} - no mínimo n vezes
* {n,m} - no mínimo n+1 vezes, no máximo m vezes 


#### Classes de char - []
* [A-Z] - letras de A até Z
* [123] - 1,2 ou 3
* \d    - todos os digitos [0-9]
* \s    - whitespace [\t\r\n\f]
* \w    - wordchar [A-Za-z0-9_]

Padrão para: 19h32min16s
```
\d{2}h[0-5]\d{1}min[0-5]\d{1}s
```
Padrão para placas: exemplo KMG-8089
```
[A-Z]{3}-\d{4}
```

###Links diretos:


Desenvolvimento
---------------------
-   [Rodolfo Peixoto](http://www.rogpe.me)
