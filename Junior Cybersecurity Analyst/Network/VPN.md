
Technology that allows a secure and encrypted connection between a private network and a remote device.
- `TCP/1723` for [Point-to-Point Tunneling Protocol](https://www.lifewire.com/pptp-point-to-point-tunneling-protocol-818182) `PPTP`
- `UDP/500` for [IKEv1](https://www.cisco.com/c/en/us/support/docs/security-vpn/ipsec-negotiation-ike-protocols/217432-understand-ipsec-ikev1-protocol.html) and [IKEv2](https://nordvpn.com/blog/ikev2ipsec/)
- This protocols in those ports does:
	- Identify
	- stablish an algorithm
	- exchange keys

Moreover, we can use VPNs to connect multiple remote locations, such as branch offices, into a single private network

### Requirments

| Requirment       | Description                                                                                                                                                             |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `VPN Client`     | This is installed on the remote device and is used to establish and maintain a VPN connection with the VPN server. For example, this could be an OpenVPN client.        |
| `VPN Server`     | This is a computer or network device responsible for accepting VPN connections from VPN clients and routing traffic between the VPN clients and the private network.    |
| `Encryption`     | VPN connections are encrypted using a variety of encryption algorithms and protocols, such as AES and IPsec, to secure the connection and protect the transmitted data. |
| `Authentication` | The VPN server and client must authenticate each other using a shared secret, certificate, or another authentication method to establish a secure connection.           |

In the TCP/IP layer uses [Encapsulating Security Payload](https://www.ibm.com/docs/en/i/7.4?topic=protocols-encapsulating-security-payload) (`ESP`) protocol to encrypt and authenticate the VPN traffic

### IPSEC

Internet Protocol Security (IPsec) is a network security protocol that provides encryption and authentication for internet communications. Works by encrypting the data payload of each IP packet and adding an authentication header (AH), which is used to verify the integrity and authenticity of the packet.

1. `Authentication Header`(`AH`): This protocol provides integrity and authenticity for IP packets but does not provide encryption. It adds an authentication header to each IP packet, which contains a cryptographic checksum that can be used to verify that the packet has not been tampered with.
    
2. `Encapsulating Security Payload` (`ESP`): This protocol provides encryption and optional authentication for IP packets. It encrypts the data payload of each IP packet and optionally adds an authentication header, similar to AH.

| **Mode**         | **Description**                                                                                                                                                                                    |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Transport Mode` | In this mode, IPsec encrypts and authenticates the data payload of each IP packet but does not encrypt the IP header. This is typically used to secure end-to-end communication between two hosts. |
| `Tunnel Mode`    | With this mode, IPsec encrypts and authenticates the entire IP packet, including the IP header. This is typically used to create a VPN tunnel between two networks.                                |

If there is a `firewall` in the middle this need to allows the following protocols:

| **Protocol**                             | **Port**    | **Description**                                                                                                                                                                                                                                                                                          |
| ---------------------------------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Internet Protocol` (`IP`)               | `UDP/50-51` | This is the primary protocol that provides the foundation for all internet communication. It is used to route packets of data between the VPN client and the VPN server.                                                                                                                                 |
| `Internet Key Exchange` (`IKE`)          | `UDP/500`   | IKE is a protocol that is used to establish and maintain secure communication between the VPN client and the VPN server. It is based on the Diffie-Hellman key exchange algorithm, and it is used to negotiate and establish shared secret keys that can be used to encrypt and decrypt the VPN traffic. |
| `Encapsulating Security Payload` (`ESP`) | `UDP/4500`  | ESP is also a protocol that provides encryption and authentication for IP datagrams. It is used to encrypt the VPN traffic between the VPN client and the VPN server, using the keys that were negotiated with IKE.                                                                                      |

### PPTP

 Is a network protocol that enables the creation of VPNs by establishing a secure tunnel between the VPN client and server, encapsulating the data transmitted within this tunnel.
 
 Depracated, nowadays there are more secure protocols like: L2TP/IPsec, IPsec/IKEv2, and OpenVPN

``` mermaid
flowchart TD

    A[Remote User / VPN Client] -->|Internet| B[VPN Server]

    subgraph Establishment["VPN Connection Establishment"]
        B1[IKE<br/>UDP 500 / UDP 4500] -->|Authentication & Key Exchange| B2[Security Association]
    end

    A --> B1
    B1 --> B2

    subgraph DataFlow["Encrypted Data Tunnel"]
        C1[User Applications<br/>HTTP / SSH / FTP] --> C2[TCP / UDP]
        C2 --> C3[IPsec - ESP<br/>IP Protocol 50]
        C3 --> C4[Encrypted IP Packets]
    end

    B2 --> C3
    C4 -->|Encrypted Tunnel| B

    B --> D[Internal Network]
    D --> E[Internal Servers]

```
