## Direccionamiento IPv4

El conocimiento del direccionamiento IP (Internet Protocol) es el inicio para un buen entendimiento sobre redes. Todos los ordenadores que están conectados a la red y que tienen como forma de comunicación el protocolo TCP / IP deben tener un número de identificación llamado IP para hablar entre sí. La versión utilizada actualmente es la V4 o IPV4 y la V6 o IPV6 ya puede ser utilizada, pero en este artículo vamos a tratar sólo de IPv4.

Las direcciones IPv4 son números de 32 bits que normalmente se muestran en notación decimal con puntos, el número de IP es el formato siguiente:
```
XXX.XXX.XXX.XXX
```

cada XXX es un entero decimal que varía de 0 a 255, es decir, un número binario de ocho bits de 00000000 a 11111111. Para saber cuántos números puedo representar se hace así: 2 ^ 8 = 256. (2 por ser binario o base 2 o representado por 0 o 1, 8 por 8 bits). Es decir, la cantidad de números que se pueden representar es de 256 números. Como son 4 grupos de 256 podemos hacer 256 * 256 * 256 * 256 = 2 ^ 32 = 4.294.967.296 números. Resumiendo el número IP tiene 32 bits y puede representar 4.294.967.296 número.

Para convertir un número decimal en binario es sólo dividirlo por 2 sucesivamente e ir anotando el resto de la división. Por ejemplo: Para convertir el número decimal 184 a binario lo hacemos así:

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

anotando los restos de abajo hacia arriba tenemos 10111000 en binario que es igual a 184 en decimal. La conversión de decimal en binario se realiza así:

```
  2⁷ 2⁶ 2⁵ 2⁴ 2³ 2² 2¹ 2⁰
128 64 32 16 8 4 2 1 calculando las potencias
  1 0 1 1 1 0 0 0 Nuestro número binario
128 + 0 + 32 + 16 + 8 + 0 + 0 + 0 multiplicando el número binario por los resultados de las potencias y sumando los resultados tenemos 184.
```

entonces un número ip 192.168.0.134 en decimal corresponde a 11000000.10101000.00000000.10000110

Este número además de identificar el número de host (equipo o equipo que tiene TCP / IP) también identifica la red a la que pertenece el host. Los primeros bits (de izquierda a derecha) del número representan en qué red el host está y los bits restantes representan el número de host dentro de la red.

## Máscara de red

La máscara de red se utiliza para poder identificar cuántos bits podemos usar para dirigir la red y cuántos bits podremos utilizar para dirigir los hosts. También tiene 32 bits y debemos establecer la parte de la red a 1 y la parte del host a 0.

```
11111111.11111111.11111111.00000000 = 255.255.255.0 o / 24
```

El número de IP con la máscara anterior va a tener 24 bits utilizados para identificar la red y 8 bits para identificar los hosts o si tengo el número IP 192.168.0.134/24 tengo el host de número 134 participante de la red 192.168.0 . Como tengo 8 bits para identificar el host que puedo tener hasta 2 ^ 8 - 2 = 254 hosts en la red 192.168.0. Como tengo 24 bits para identificar la red que puedo tener 2 ^ 24 = 16.777.216 redes.

Nota: Siempre debemos sustraer la cantidad total de IP de los hosts por 2. Pues, la primera IP se utiliza para identificar la red, que en este caso es 192.168.0.0 y el último para la difusión que es esencial durante el envío del mismo mensaje a todos los dispositivos en la red local, siendo 192.168.0.255. Entonces podremos dirigir los hosts comenzando desde el IP: 192.168.0.1 y terminando en el 192.168.0.254.

Otros ejemplos:

```
11111111.11111111.00000000.00000000 = 255.255.0.0 o / 16 → 2 ^ 16 - 2 = 65534 hosts y 2 ^ 16 = 65536 redes 11111111.0000000000 = 255.0.0.0 o / 8 → 2 ^ 24 - 2 = 16.777.214 hosts y 2 ^ 8 = 256 redes
```

Podemos también:

```
11111111.11111111.11111111.11100000 = 255.255.255.224 o / 27 → 2 ^ 5 - 2 = 30 hosts y 2 ^ 27 = 134.217.728 redes 11111111.11111111.11111100.00000000 = 255.255.252.0 o / 22 → 2 ^ 18 - 2 = 1022 hosts y 2 ^ 22 = 4.194.304 redes
```

A continuación tenemos un ejemplo que una red / 20 siendo transformada en 16 redes / 24

```
187.0.176 / 24 187.0.176 / 23 187.0.176 / 22 187.0.176 / 21 187.0.176 / 20
187.0.177 / 24
187.0.178 / 24 187.0.178 / 23
187.0.179 / 24
187.0.180 / 24 187.0.180 / 23 187.0.180 / 22
187.0.181 / 24
187.0.182 / 24 187.0.182 / 23
187.0.183 / 24
187.0.184 / 24 187.0.184 / 23 187.0.184 / 22 187.0.184 / 21
187.0.185 / 24
187.0.186 / 24 187.0.186 / 23
187.0.187 / 24
187.0.188 / 24 187.0.188 / 23 187.0.188 / 22
187.0.189 / 24
187.0.190 / 24 187.0.190 / 23
187.0.191 / 24
```

Un host puede hablar directamente con otros hosts desde que estén en la misma red. Para hablar con hosts de otras redes es necesario que hay una o más gateways interconectando las redes.

El direccionamiento ip tiene algunos detalles a ser observados.

- El primer número ip de un rango se utiliza para la red y el último se utiliza para la difusión, no pudiendo ser utilizados en hosts.
- El número ip 127.0.0.1 se utiliza para identificar el localhost
- Las redes 10/8 176.16 / 16 y 192.168 / 24 son redes privadas

## Definiciones

- IP pública - número IP que se puede enrutar en Internet
- IP privada - número IP que no se puede enrutar en Internet y sirve para ser utilizado en redes privadas
- IP no válida - número que no existe, por ejemplo: 350.152.854.1
- IP fija o estática - número ip asignado a un host y no se cambiará a cada conexión
- IP dinámica - número IP que se asigna dinámicamente y se puede cambiar a cada asignación

## Referencias

http://grsecurity.com.br/apostilas/TCP/training-networking-tcpip.pdf

http://pages.di.unipi.it/ricci/501302.pdf
