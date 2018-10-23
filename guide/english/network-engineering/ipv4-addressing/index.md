## IPv4 Addressing

Knowledge of Internet Protocol (IP) addressing is the beginning of a good understanding of networks. All computers that are interconnected in network (s) and have as form of communication the protocol TCP / IP need to have an identification number called IP to talk to each other. The version currently used is V4 or IPV4 and V6 or IPV6 can already be used, but in this article we will treat only IPv4.

IPv4 addresses are 32-bit numbers that are normally displayed in dotted decimal notation, the IP number defaults to the following format:

```
XXX.XXX.XXX.XXX
```

each XXX is a decimal integer that ranges from 0 to 255, that is, a binary number of eight bits from 00000000 to 11111111. To know how many numbers I can represent it is as follows: 2 ^ 8 = 256. (2 because it is binary or base 2 or represented by 0 or 1.8 by having 8 bits). In other words, the number of numbers that can be represented is 256 numbers. As there are 4 groups of 256 we can make 256 * 256 * 256 * 256 = 2 ^ 32 = 4,294,967,296 numbers. Summing up the IP number has 32 bits and can represent 4,294,967,296 number.

To convert a decimal number to binary it is only divide it by 2 successively and go annotating the rest of the division. For example: To convert the decimal number 184 to binary we do so:

```
 184/2 = 92 leftover 0
  92/2 = 46 leftover 0
  46/2 = 23 leftover 0
  23/2 = 11 leftover 1
   11/2 = 5 leftover 1
   5/2 = 2 leftover 1
   2/2 = 0 leftover 0
   1/2 = 0 leftover 1
```

noting the remains from the bottom up we have 10111000 in binary which is equal to 184 in decimal. Conversion from decimal to binary is done like this:

```
 2⁷ 2⁶ 2⁵ 2⁴ 2³ 2² 2¹ 2⁰
128 64 32 16 8 4 2 1 calculating the powers
  1 0 1 1 1 0 0 0 our binary number
128 + 0 + 32 + 16 + 8 + 0 + 0 + 0 multiplying the binary number by the results of the powers and adding the results we have 184.
```
hen a 192.168.0.134 ip number in decimal corresponds to 11000000.10101000.00000000.10000110

This number in addition to identifying the host number (computer or equipment that has TCP / IP) it also identifies which network the host belongs to. The first bits (from left to right) of the number represent what network the host is on and the remaining bits represent the host number within the network.

## Network mask

The network mask is used to identify how many bits we can use to address the network and how many bits we can use to address the hosts. It also has 32 bits and we should set the network part to 1 and the host part to 0.


```
11111111.11111111.11111111.00000000 = 255.255.255.0 or / 24
```
The IP number with the mask above will have 24 bits used to identify the network and 8 bits to identify the hosts ie if I have the IP number 192.168.0.134/24 I have the host number 134 network participant 192.168.0 . Since I have 8 bits to identify the host I can have up to 2 ^ 8 - 2 = 254 hosts on the 192.168.0 network. Since I have 24 bits to identify the network I might have 2 ^ 24 = 16,777,216 networks.

Note: We must always subtract the total number of IPs from the hosts by 2. For the first IP is used to identify the network, which in this case is 192.168.0.0 and the last one for the broadcast that is essential when sending the same message to all devices on the local network, being 192.168.0.255. Then we will be able to address the hosts starting from IP: 192.168.0.1 and ending at 192.168.0.254.

Another examples:

```
11111111.11111111.00000000.00000000 = 255.255.0.0 or / 16 → 2 ^ 16-2 = 65534 hosts and 2 ^ 16 = 65536 networks 11111111.00000000.00000000.00000000 = 255.0.0.0 or / 8 → 2 ^ 24-2 = 16,777,214 hosts and 2 ^ 8 = 256 networks
```

We can also:

```
11111111.11111111.11111111.11100000 = 255.255.255.224 ou / 27 → 2 ^ 5-2 = 30 hosts and 2 ^ 27 = 134.217.728 networks 11111111.11111111.11111100.00000000 = 255.255.252.0 or / 22 → 2 ^ 18-2 = 1022 hosts and 2 ^ 22 = 4,144,304 networks
```

Below we have an example that a network / 20 being transformed into 16 networks / 24

```
187.0.176 / 24 187.0.176 / 23 187.0.176 / 22 187.0.176 / 21 187.0.176 / 21
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

A host can talk directly to other hosts as long as they are on the same network. To talk to hosts on other networks you need to have one or more gateways interconnecting the networks.

The ip address has some details to observe.

- The first ip number of a range is used for the network and the last one is used for broadcast, and can not be used on hosts.
- The ip number 127.0.0.1 is used to identify localhost
- The networks 10/8 176.16 / 16 and 192.168 / 24 are private networks

## Definitions

- public IP - IP number that can be routed on the internet
- Private IP - IP number that can not be routed on the internet and is intended to be used on private networks
- Invalid IP - number that does not exist, for example: 350.152.854.1
- Fixed or static IP - ip number assigned to a host and will not be changed every time
- Dynamic IP - IP number that is assigned dynamically and can be changed with each assignment

## References

http://grsecurity.com.br/apostilas/TCP/training-networking-tcpip.pdf

http://pages.di.unipi.it/ricci/501302.pdf



