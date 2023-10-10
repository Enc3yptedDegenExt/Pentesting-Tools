Contributer
==
Name: Gaurav Motling
Intern ID: HPTI-SEP23-090

## Firewalk
Firewalk is an active reconnaissance network security tool that attempts to determine what layer 4 protocols a given IP forwarding device will pass. It works by sending out TCP or UDP packets with a TTL one hop greater than the targeted gateway. If the gateway allows the traffic, it will forward the packets to the next hop where they will expire and elicit an ICMP_TIME_EXCEEDED message. Otherwise, it will likely drop the packets and there will be no response.

To get the correct IP TTL that will result in packets expiring one hop beyond the gateway, Firewalk needs to ramp up hop counts. It does this in the same manner that traceroute works. Once the scan is bound (that is, Firewalk knows the gateway hop count), it begins the scan. The ultimate destination host does not have to be reached, it only needs to be somewhere downstream, on the other side of the gateway, from the scanning host.

Firewalk helps in assessing the security configuration of packet filtering devices, such as those used in firewall systems. It is relevant for network security assessments, like network penetration tests (pentests).

## Overview

1. [Installation](#Installation)
2. [Dependencies](#Dependencies)
3. [Quick Start](#Quick-Start)
4. [Example](#Example)

## Installation
**How to install:** sudo apt install firewalk

![install](https://github.com/Gmotzz/HPTI-SEP-2023/assets/147436807/864b3be9-52d9-478f-b5a1-87827d93a6dc)



## Dependencies

**libc6**
**libdumbnet1**
**libnet1**
**libpcap0.8**

![depend](https://github.com/Gmotzz/HPTI-SEP-2023/assets/147436807/8c67dff9-743a-4ebd-b312-faeabd4ab840)

## Quick Start
**firewalk**

![qs](https://github.com/Gmotzz/HPTI-SEP-2023/assets/147436807/eba38469-d011-4d64-ade3-25756750106a)


## Example

![example](https://github.com/Gmotzz/HPTI-SEP-2023/assets/147436807/6cb8b837-fe80-4abd-9ebb-b36609399a41)


