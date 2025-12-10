
### Network types

`LAN`: Local network within a home, office, or campus. Uses private RFC 1918 addressing.

`WLAN`: A LAN delivered wirelessly via Wi-Fi. Functionally identical to a LAN but over RF.

`WAN`: Connects multiple LANs over large geographic areas. The Internet is the canonical WAN. Uses WAN-level routing (e.g., BGP) and public IP space.

`VPN`: Provides virtual access to a remote network.
- **Site-to-Site**: connects entire networks via routers/firewalls.
- **Remote Access**: client device creates a virtual interface (TUN/TAP). May be split-tunnel or full-tunnel.
- **SSL VPN**: browser-based VPN that streams apps or desktops.

`GAN`: Global network that interconnects multiple WANs

`MAN`: Metropolitan network linking several LANs within a city/region using high-capacity fiber links

`PAN/WPAN`: Short-range personal networks. PAN (wired). WPAN (Bluetooth, ZigBee, Z-Wave). Common in IoT and personal devices.

### Networking Topologies

**Connections**
`wired`: Coaxial cabling, glass fiber cabling, twisted-pair cabling...
`wireless`: Wi-Fi, cellular, satellite...

**Nodes** (NIC)
`Repeaters`: Hubs, Switches and Bridges
`Router/Modem`: Getaways and firewalls

**Classification**
- Physical: how are connected
- Logical: how the traffic flows

`Point-to-Point`: 
![[Pasted image 20251210140503.png]]
`Bus`: Transmitted through a coaxial cable, all hosts receive the traffic.
![[Pasted image 20251210140542.png]]
`Star`: Has a central network component
![[Pasted image 20251210140759.png]]
`Ring`: Each host or node has two connections, one for incoming traffic and one for the outgoing
![[Pasted image 20251210141006.png]]
`Mesh`: Two types
- Fully meshed: Each host connected to every host (used in WAN and MAN)
- Partially meshed: Specific nodes are connected to exactly one other node, and some other nodes are connected to two or more other nodes with a point-to-point connection
![[Pasted image 20251210141546.png]]
`Tree`: 
![[Pasted image 20251210141655.png]]
`Hybrid`: Two different basic network topologies are interconnected
![[Pasted image 20251210141859.png]]
`Daisy Chain`: Multiple hosts are connected by placing a cable from one node to another. Used in CAN (automatation chain technologies)
![[Pasted image 20251210142025.png]]
