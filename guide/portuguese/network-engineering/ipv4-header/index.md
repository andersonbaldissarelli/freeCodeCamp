
## Cabeçalho IPv4

![IPv4 Header](http://ipv6.br/media/noticias/cabecalho-01.jpg)

O cabeçalho IPv4 é composto por 12 campos fixos, que podem ou não conter opções responsáveis por fazer com que o tamanho varie de 20 a 60 Bytes. Estes campos são destinados transmitir informações sobre:

#### Version
- 4 bits
- Indica o formato do cabeçalho, podendo ser Ipv4 ou Ipv6.

#### IHL (Internet Header Length)
- 4 bits
- Indica o tamanho do cabeçalho em palavras de 32 bits, o valor mínimo correto é 20.

#### Type of Service
- 8 bits
- Especifica o tratamento que o datagrama deve receber dos roteadores durante seu percurso.

#### Total Length
- 16 bits
Especifica o tamanho do datagrama, considerando o cabeçalho IP mais a área de dados.

#### Identification
- 16 bits
- Valor designado pelo emissor usado na remontagem dos datagramas no destino.

#### Flags
- 3 bits
- Controlam a fragmentação da mensagem.

Bit 0: reservado, deve ser zero

Bit 1: (DF) 0= Might Fragment, 1 = Don’t Fragment

Bit 2: (MF) 0 = Last Fragment, 1 = More Fragments

#### Fragment Offset
- 13 bits
- Na montagem da mensagem, indica a posição dos dados do datagrama, por exemplo, analise os pacotes 1 a 5 do trace ipfragment.cap. Ao passar por um roteador, um pacote único foi fragmentado em 5 datagramas, que chegaram na ordem 1, 2, 3, 4 e 5 no destinatário. Esta ordem, porém, não é a ordem correta dos dados. Com base na informação do campo Fragment Offset, a ordem correta foi encontrada, como sendo 4, 5, 2, 3, 1.

#### Time-to-live
- 8 bits
- Usado para controlar o tempo de existência do datagrama. Ao passar por um roteador, o valor deste campo é reduzido em 1. Se o valor chegar a 0, o datagrama é descartado pelo roteador.

#### Protocol
- 8 bits
- Identifica o protocolo inserido no próximo nível, conforme especificados na RFC 790. Com base nesta informação, o datagrama será enviado ao software respectivo, responsável pelo tratamento do protocolo especificado.

#### Header Checksum
- 16 bits
- Usado para verificação de erros no cabeçalho IP. Não serve para verificar erros nos dados.

#### Source Address
- 32 bits
- Contém o endereço lógico do remetente; será discutido no próximo módulo.

#### Destination Address
- 32 Bits
- Contém o endereço lógico do nó de destino; será discutido no próximo módulo.

#### Options
De tamano variável, é um campo não obrigatório, usado primariamente para testes e debugs. Normalmente não é utilizado.
O sistema saberá se há ou não instruções aqui através do campo IHL.

#### Padding
Previsão para completar o espaço, caso Options seja utilizado.


## Mais informações

https://advancedinternettechnologies.wordpress.com/ipv4-header/
