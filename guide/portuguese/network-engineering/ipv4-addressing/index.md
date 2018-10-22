## Endereçamento IPv4

O conhecimento do endereçamento IP (Internet Protocol) é o início para um bom entendimento sobre redes. Todos os computadores que estão interligados em rede(s) e tem como forma de comunicação o protocolo TCP/IP precisam ter um número de identificação chamado IP para falarem entre si. A versão utilizada atualmente é a V4 ou IPV4 e a V6 ou IPV6 já pode ser utilizada, mas neste artigo vamos tratar apenas do IPv4.

Endereços IPv4 são números de 32 bits que são normalmente exibidos em notação decimal com pontos, o número de IP tem como padrão o seguinte formato: 

```
XXX.XXX.XXX.XXX
```
cada XXX é um número inteiro decimal que vária de 0 a 255, ou seja, um número binário de oito bits de 00000000 a 11111111. Para saber quantos números posso representar faz-se assim: 2^8 = 256. (2 por ser binário ou base 2 ou representado por 0 ou 1, 8 por ter 8 bits). Ou seja a quantidade de números que podem ser representados é de 256 números. Como são 4 grupos de 256 podemos fazer 256*256*256*256 = 2^32 = 4.294.967.296 números. Resumindo o número IP tem 32 bits e pode representar 4.294.967.296 número.

Para converter um número decimal em binário é só dividí-lo por 2 sucessivamente e ir anotando o resto da divisão. Por exemplo: Para converter o número decimal 184 para binário fazemos assim:

```
 184/2 = 92 sobra 0
  92/2 = 46 sobra 0
  46/2 = 23 sobra 0
  23/2 = 11 sobra 1
   11/2 = 5 sobra 1
   5/2 = 2 sobra 1
   2/2 = 0 sobra 0
   1/2 = 0 sobra 1
```
anotando os restos de baixo para cima temos 10111000 em binário que é igual a 184 em decimal. A conversão de decimal em binário é feita assim: 

```
  2⁷   2⁶   2⁵   2⁴   2³   2²   2¹   2⁰
128   64   32   16    8    4    2    1  calculando as potências
  1    0    1    1    1    0    0    0  nosso número binário
128  + 0 + 32 + 16 +  8 +  0 +  0 +  0  multiplicando o número binário pelos resultados das potências e somando os resultados temos 184.
```
então um número ip 192.168.0.134 em decimal corresponde a 11000000.10101000.00000000.10000110

Este número além de identificar qual o número do host (computador ou equipamento que possui o TCP/IP) ele também identifica qual a rede a qual o host pertence. Os primeiros bits (da esquerda para a direta) do número representam em qual rede o host está e os bits restantes representas o número do host dentro da rede.

## Máscara de rede

A máscara de rede é utilizada para podermos identificar quantos bits podemos usar para endereçar a rede e quantos bits poderemos utilizar para endereçar os hosts. Ela também tem 32 bits e devemos setar a parte da rede para 1 e a parte do host para 0.

```
11111111.11111111.11111111.00000000 = 255.255.255.0 ou /24
```
O número de IP com a máscara acima vai ter 24 bits usados para identificar a rede e 8 bits para identificar os hosts ou seja se eu tiver o número IP 192.168.0.134/24 eu tenho o host de número 134 participante da rede 192.168.0. Como eu tenho 8 bits para identificar o host eu poderei ter até 2^8 - 2 = 254 hosts na rede 192.168.0. Como eu tenho 24 bits para identificar a rede eu poderei ter 2^24 = 16.777.216 redes.

Observação: Sempre devemos subtrair a quantidade total de IPs dos hosts por 2. Pois, o primeiro IP é utilizado para identificar a rede, que neste caso é 192.168.0.0 e o último para o broadcast que é essencial durante o envio da mesma mensagem para todos os dispositivos na rede local, sendo 192.168.0.255. Então poderemos endereçar os hosts começando do IP: 192.168.0.1 e terminando no 192.168.0.254.

Outros exemplos:

```
11111111.11111111.00000000.00000000 = 255.255.0.0 ou /16 → 2^16 - 2 = 65534 hosts e 2^16 = 65536 redes 11111111.00000000.00000000.00000000 = 255.0.0.0 ou /8 → 2^24 - 2= 16.777.214 hosts e 2^8 = 256 redes
```

Podemos ainda:

```
11111111.11111111.11111111.11100000 = 255.255.255.224 ou /27 → 2^5 - 2 = 30 hosts e 2^27 = 134.217.728 redes 11111111.11111111.11111100.00000000 = 255.255.252.0 ou /22 → 2^18 - 2= 1022 hosts e 2^22 = 4.194.304 redes
```

Abaixo temos um exemplo que uma rede /20 sendo transformada em 16 redes /24

```
187.0.176/24	187.0.176/23	187.0.176/22	187.0.176/21	187.0.176/20
187.0.177/24	
187.0.178/24	187.0.178/23	
187.0.179/24	
187.0.180/24	187.0.180/23	187.0.180/22	
187.0.181/24	
187.0.182/24	187.0.182/23	
187.0.183/24	
187.0.184/24	187.0.184/23	187.0.184/22	187.0.184/21	
187.0.185/24	
187.0.186/24	187.0.186/23	
187.0.187/24	
187.0.188/24	187.0.188/23	187.0.188/22	
187.0.189/24	
187.0.190/24	187.0.190/23	
187.0.191/24	
```

Um host pode falar diretamente com outros hosts desde que eles estejam na mesma rede. Para falar com hosts de outras redes é preciso que existe um ou mais gateways interligando as redes.

O endereçamento ip tem alguns detalhes a serem observados.

- O primeiro número ip de um range é usado para a rede e o último é usado para broadcast, não podendo ser usados em hosts.
- O número ip 127.0.0.1 é usado para identificar o localhost
- As redes 10/8 176.16/16 e 192.168/24 são redes privadas

## Definições

- IP público - número IP que pode ser roteado na internet
- IP privado - número IP que não pode ser roteado na internet e serve para ser usando em redes privadas
- IP inválido - número que não existe, por exemplo: 350.152.854.1
- IP fixo ou estático - número ip atribuído a um host e não será alterado a cada conexão
- IP dinâmico - número IP que é atribuído dinamicamente e pode ser alterado a cada atribuição

## Referências

http://grsecurity.com.br/apostilas/TCP/training-networking-tcpip.pdf

http://pages.di.unipi.it/ricci/501302.pdf

