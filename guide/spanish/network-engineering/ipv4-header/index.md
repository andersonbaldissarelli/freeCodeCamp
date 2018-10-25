## Encabezado IPv4

![IPv4 Header](http://ipv6.br/media/noticias/cabecalho-01.jpg)

El encabezado IPv4 se compone de 12 campos fijos, que pueden o no contener opciones responsables de hacer que el tamaño varía de 20 a 60 Bytes. Estos campos se destinan a transmitir información sobre:

#### Version
- 4 bits
- Indica el formato del encabezado, pudiendo ser Ipv4 o Ipv6.

#### IHL (Internet Header Length)
- 4 bits
- Indica el tamaño del encabezado en palabras de 32 bits, el valor mínimo correcto es 20.

#### Type of Service
- 8 bits
- Especifica el tratamiento que el datagrama debe recibir de los routers durante su recorrido.

#### Length Length:
- 16 bits
Especifica el tamaño del datagrama, considerando el encabezado IP más el área de datos.

#### Identification
- 16 bits
- Valor designado por el emisor utilizado en el remontaje de los datagramas en el destino.

#### Flags
- 3 bits
- Controlan la fragmentación del mensaje.

Bit 0: reservado, debe ser cero

Bit 1: (DF) 0 = Might Fragment, 1 = Do not Fragment

Bit 2: (MF) 0 = Last Fragment, 1 = Más Fragmentos

#### Fragment Offset
- 13 bits
- En el montaje del mensaje, indica la posición de los datos del datagrama, por ejemplo, analice los paquetes 1 a 5 del trace ipfragment.cap. Al pasar por un enrutador, un paquete único fue fragmentado en 5 datagramas, que llegaron en el orden 1, 2, 3, 4 y 5 en el destinatario. Este orden, sin embargo, no es el orden correcto de los datos. Con base en la información del campo Fragment Offset, el orden correcto fue encontrado, como siendo 4, 5, 2, 3, 1.

#### Time-to-live
- 8 bits
- Utilizado para controlar el tiempo de existencia del datagrama. Al pasar por un enrutador, el valor de este campo se reduce en 1. Si el valor llega a 0, el datagrama es descartado por el router.

#### Protocol
- 8 bits
- Identifica el protocolo introducido en el siguiente nivel, según se especifica en la RFC 790. Basándose en esta información, el datagrama será enviado al software respectivo, responsable del tratamiento del protocolo especificado.

#### Header Checksum
- 16 bits
- Utilizado para la verificación de errores en el encabezado IP. No sirve para verificar errores en los datos.

#### Source Address
- 32 bits
- Contiene la dirección lógica del remitente; se discutirá en el siguiente módulo.

#### Destination Address
- 32 Bits
- Contiene la dirección lógica del nodo de destino; se discutirá en el siguiente módulo.

#### Options
De tamano variable, es un campo no obligatorio, usado principalmente para pruebas y debugs. Normalmente no se utiliza.
El sistema sabrá si hay o no instrucciones aquí a través del campo IHL.

#### Padding
La previsión para completar el espacio, si se utiliza Options.


## Mas informaciones

https://advancedinternettechnologies.wordpress.com/ipv4-header/

