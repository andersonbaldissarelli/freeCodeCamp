## IPv6 Header

IPv6 introduces a new format to the header to make it simpler.

![IPv6 Header](http://ipv6.br/media/noticias/cabecalho-021.jpg)

All fields in this new header have a fixed length totaling 64 bytes. The fact of having a fixed size greatly expedites the processing of the packets by the routers, since there is no need to calculate the length of certain fields nor the size of the header as a whole. In addition there was a reduction of field numbers used by means of fields with little utility in practice.

#### Version
- 4 bits
- Identifies the version of the protocol used. In this case, the value of this field is 6.

#### Traffic Class
- 8 bits
- Identifies the packages by service class or priority. It provides the same functionality and definitions as the "IPv4 Service Type" field.

#### Flow Identifier
- 20 bits
- Identifies packets of the same communication stream. Ideally this field is configured by the destination address to separate the streams from each of the applications and the network intermediary nodes can use it in aggregate with the source and destination addresses to perform specific handling of the packets.

#### Data Size
16-bit
- Indicates the size, in Bytes, of the data sent next to the IPv6 header. Replaced the Total Size field of IPv4, which indicated the size of the header plus the size of the transmitted data. However, the size of the extension headers are also added in this new field.

#### Next Header
- 8 bits
- Identifies the extension header that follows the current one. It was renamed (in IPv4 it was called Protocol) to reflect the new organization of the IPv6 packets, since it no longer contains values ​​referring to other protocols, to indicate the types of extension headers.

#### Routing Limit
- 8 bits
- This field is decremented with each routing hop and indicates the maximum number of routers that the packet can pass before being dropped. It standardized how the IPv4 Time-of-Life (TTL) field was being used, which differed significantly from the original description that defined it as the time, in seconds, for the packet to be dropped if it did not reach its destination.

#### Source address
- 128 bit
- Indicates the source address of the packet.

#### Destination address
- 128 bit
- Indicates the destination address of the packet.

#### More information

http://ipv6.br/post/cabecalho/

https://tools.ietf.org/html/rfc2460
