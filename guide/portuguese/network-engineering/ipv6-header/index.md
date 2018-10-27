## Cabeçalho IPv4

O IPv6 introduz um novo formato ao cabeçalho, de modo a torna-lo mais simples.

![IPv6 Header](http://ipv6.br/media/noticias/cabecalho-021.jpg)


Todos os campos deste novo cabeçalho possuem um tamanho fixo totalizando 64 bytes. O fato de ter um tamanho fixo acelara bastante o processamento dos pacotes pelos roteadores, visto que não há a necessidade de calcular a extenso de certos campos e nem o tamanho do cabeçalho como um todo. Além disso ocorreu uma redução de números de campos utilizados por meio de campos com pouca utilidade na prática.

#### Versão 
- 4 bits 
- Identifica a versão do protocolo utilizado. No caso, o valor desse campo é 6.

#### Classe de Tráfego 
- 8 bits 
- Identifica os pacotes por classes de serviços ou prioridade. Ele provê as mesmas funcionalidades e definições do campo "Tipo de Serviço do IPv4".

#### Identificador de Fluxo 
- 20 bits
- Identifica pacotes do mesmo fluxo de comunicação. Idealmente esse campo é configurado pelo endereço de destino para separar os fluxos de cada uma das aplicações e os nós intermediários de rede podem utiliza-lo de forma agregada com os endereços de origem e destino para realização de tratamento específico dos pacotes.

#### Tamanho do Dados 
- 16 bits
- Indica o tamanho, em Bytes, apenas dos dados enviados junto ao cabeçalho IPv6. Substituiu o campo Tamanho Total do IPv4, que indicava o tamanho do cabeçalho mais o tamanho dos dados transmitidos. Contudo, o tamnho dos cabeçalhos de extensão também são somado nesse novo campo.

#### Próximo Cabeçalho 
- 8 bits
- Identifica o cabeçalho de extensão que segue o atual. Ele foi renomeado (no IPv4 chamava-se Protocolo) para refletir a nova organização dos pacotes IPv6, uma vez que ele deixou de conter os valores referentes a outros protocolos, para indicar os tipos dos cabeçalhos de extensão.

#### Limite de Encaminhamento 
- 8 bits
- Esse campo é decrementado a cada salto de roteamento e indica o número máximo de roteadores pelos quais o pacote pode passar antes de ser descartado. Ele padronizou o modo como o campo Tempo de Vida (TTL) do IPv4 vinha sendo utilizado, o qual diferia significativamente da descrição original que o definia como o tempo, em segundos, para o pacote ser descartado caso não chegasse à seu destino.

#### Endereço de origem 
- 128 bits
- Indica o endereço de origem do pacote.

#### Endereço de Destino 
- 128 bits
- Indica o endereço de destino do pacote.

#### Mais informações

http://ipv6.br/post/cabecalho/




