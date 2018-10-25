## IPv4 Header

![IPv4 Header](http://ipv6.br/media/noticias/cabecalho-01.jpg)

The IPv4 header consists of 12 fixed fields, which may or may not contain options responsible for making the size range from 20 to 60 Bytes. These fields are intended to convey information about:

#### Version
- 4 bits
- Indicates the format of the header, being it can be Ipv4 or Ipv6.

#### IHL (Internet Header Length)
- 4 bits
- Indicates the header size in 32-bit words, the correct minimum value is 20.

#### Type of Service
- 8 bits
- Specifies how the datagram should receive from the routers during its route.

#### Total Length
16-bit
Specifies the size of the datagram, considering the IP header plus the data area.

#### Identification
16-bit
- Value designated by the sender used to reassemble the datagrams at the destination.

#### Flags
- 3 bits
- Control the fragmentation of the message.

Bit 0: Reserved, must be zero

Bit 1: (DF) 0= Might Fragment, 1 = Don’t Fragment

Bit 2: (MF) 0 = Last Fragment, 1 = More Fragments

#### Fragment Offset
- 13 bits
- In the message assembly, it indicates the position of the datagram data, for example, analyze packages 1 to 5 of trace ipfragment.cap. When passing through a router, a single packet was fragmented into 5 datagrams, which arrived in order 1, 2, 3, 4, and 5 at the recipient. This order, however, is not the correct order of the data. Based on information from the Fragment Offset field, the correct order was found to be 4, 5, 2, 3, 1.

#### Time-to-live
- 8 bits
- Used to control the lifetime of the datagram. When passing through a router, the value of this field is reduced by 1. If the value reaches 0, the datagram is discarded by the router.

#### Protocol
- 8 bits
- Identifies the protocol inserted at the next level, as specified in RFC 790. Based on this information, the datagram will be sent to the respective software, responsible for handling the specified protocol.

#### Header Checksum
16-bit
- Used to check for errors in the IP header. Not for error checking data.

#### Source Address
- 32 bit
- Contains the logical address of the sender; will be discussed in the next module.

#### Destination Address
- 32 bits
- Contains the logical address of the destination node; will be discussed in the next module.

#### Options
Variable size, is a non-mandatory field, used primarily for testing and debugging. Usually not used.
The system will know whether or not there are instructions here through the IHL field.

#### Padding
Forecast to complete the space, if Options is used.


## More information

https://advancedinternettechnologies.wordpress.com/ipv4-header/
