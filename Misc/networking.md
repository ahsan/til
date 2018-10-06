# IPv4

- 32 bits long
- Divided into four chunks called 'Octets'


| Class | First Octet Range | Network ID Octet(s) | Host ID Octet(s) | Default Subnet Mask |
|---|---|---|---|---|
A | 0-126 | First | Last three | 255.0.0.0 |
B | 128-191 | First two | Last two | 255.255.0.0 |
C | 191-131 | First three | Fourth | 255.255.255.0 |

## Private and Public IP Addresses
- Due to the limited address space in IPv4, some addresses have been dedicated to be used within LAN only. These are Private IP addresses. Public IP addresses are required to connect to the internet. Private ranges can be used freely without any restrictions.

| Class | Private IP Range |
|---|---|
|A|**10**.0.0.0 - **10**.255.255.255|
|B|172.**16**.0.0 - 172.**31**.255.255|
|C|192.**168**.0.0 - 192.**168**.255.255|

A router provides internet access to a private network.


# CIDR Notation
- Stands for 'Classless Inter Domain Routing'.
- a.b.c.d/X where X represents the number of 1s in the subnet mask.

# Subnetting
- A subnet mask must have no zero in a position greater than the LSB.

Steps for subnetting ([Berry Smith](https://www.youtube.com/watch?v=gOOPP-ceToc)):

1. Determine the IP address class.
2. Determine the network and node ID.
3. Apply default subnet mask.
4. Convert subnet mask to binary.
5. Use the formula: (2**n - 2) to determine the custom subnet masks.

> Example: Make 11 subnets for 172.16.0.0
1. The first octet lies between 128-191, hence it is class B.
2. Network ID: first two octets __172.16__.0.0; Host ID: last two octets 172.16.__0.0__

| | Network | | Host | |
|---|---|---|---|---|
| Base IP | 172. | 16. | 0. | 0 |

3. Default subnet mask for class B is 255.255.0.0

| | Network | | Host | |
|---|---|---|---|---|
| Base IP | 172. | 16. | 0. | 0 |
| Default Subnet Mask| 255. | 255. | 0. | 0 |

4. Default subnet mask in binary:

| | Network | | Host | |
|---|---|---|---|---|
| Base IP | 172. | 16. | 0. | 0 |
| Default Subnet Mask | 255. | 255. | 0. | 0 |
| | 11111111. | 1111111. | 00000000. | 00000000  |

5. Now we have to divide the network into atleast 11 subnetworks. A subnet mask that is 4 bits long can provide us with 14 starting subnet addresses. (3 => 6)

(2**n - 2) >= 11

=> n = 4

| | Network | | Host | |
|---|---|---|---|---|
| Base IP | 172. | 16. | 0. | 0 |
| Default Subnet Mask | 11111111. | 1111111. | 00000000. | 00000000  |
| Custom Subnet Mask | 11111111. | 1111111. | **1111**0000. | 00000000  |

Which meants that the custom subnet mask is: 255.255.240.0

6. The LSB in the custom subnet mask is at the 4th power of 2. LSB = 16. The jump in the subnet is gonna be at a distance of 16 in the third octet.

7. Network addresses:

| Subnet | First IP address | Last IP address |
|---|---|---|
| 1 | 172.16.**16**.0 | 127.16.**31**.255 |
| 2 | 172.16.**32**.0 | 127.16.**47**.255 |
| 3 | 172.16.**48**.0 | 127.16.**63**.255 |
| 4 | 172.16.**64**.0 | 127.16.**79**.255 |
| 5 | 172.16.**80**.0 | 127.16.**95**.255 |
| 6 | 172.16.**96**.0 | 127.16.**111**.255 |
| 7 | 172.16.**112**.0 | 127.16.**127**.255 |
| 8 | 172.16.**128**.0 | 127.16.**143**.255 |
| 9 | 172.16.**144**.0 | 127.16.**159**.255 |
| 10 | 172.16.**160**.0 | 127.16.**175**.255 |
| 11 | 172.16.**176**.0 | 127.16.**191**.255 |
| 12 | 172.16.**192**.0 | 127.16.**207**.255 |
| 13 | 172.16.**208**.0 | 127.16.**223**.255 |
| 14 | 172.16.**224**.0 | 127.16.**239**.255 |