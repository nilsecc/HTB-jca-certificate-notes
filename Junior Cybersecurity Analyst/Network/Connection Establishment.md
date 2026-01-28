
# Key Exchange

Allow two parties to exchange cryptographic keys securely.

**Diffie-Hellman**

- Agree on a key without previous messages
- Used in `TLS` (encryption for HTTP messages)

![[Pasted image 20260128123426.png]]

**RSA**

- Based on large prime numbers `p` and `q`
- Security relies on the difficulty of factoring n (n = p*q)
- Used in encryption and `signing`
- Also in `SSL` and `TLS`
- PKINIT used by kerberos
	- Uses public key cryptography (certificates)
	- The user authenticates using a private key
	- No password-derived key is sent
	- The user proves possession of the private key via a challenge–response
- Protecting sensible data

![[Pasted image 20260128125016.png]]

**ECDSA**

Elliptic Curve Digital Signature Algorithm uses ECC (Elliptic Curve Criptography) 
- Used for example in Bitcoin for generating pubKeys
![[Pasted image 20260128125300.png]]
---

![[Pasted image 20260128125753.png]]

# IKE (Internet Key Exchange)

Protocol IKE is used to securely negotiate cryptographic keys and authenticate peers for IPsec, which operates at the IP layer and can encrypt all traffic, such as in VPNs. Application-layer protocols like HTTPS may still use TLS on top of IPsec.
- Used In VPN
- Uses DH and cryptographic functions to exchange keys and parameters for encripting traffic
- DH can use RSA for key exchange and digital signatures and AES for ecripting data

**main mode**
- Default mode of IKE and more secure. 
- 3 phases each one exchanging different parameters
- slower

**Agressive mode**
- 2 phases, all parameters sent in the first
- faster

**PSK (Pre-Shared Keys)**
- Secret value shared between two parties 
- It authentificates the client to start an IKE with the VPN service for example
- Difficult to find a way to share this key before the IKE

```
CLIENTE                               SERVIDOR VPN
   |                                       |
   |---- (1) IKE_SA_INIT ----------------->|
   |      - algoritmos                     |
   |      - nonce                          |
   |      - Diffie-Hellman (valor público) |
   |                                       |
   |<--- (2) IKE_SA_INIT ------------------|
   |      - algoritmos elegidos            |
   |      - nonce                          |
   |      - Diffie-Hellman (valor público) |
   |                                       |
   |==== Ambos calculan CLAVE SECRETA =====|
   |==== (gracias a Diffie-Hellman) =======|
   |                                       |
   |---- (3) IKE_AUTH -------------------->|
   |      - ID del cliente                 |
   |      - AUTH (calculado usando PSK)    |
   |      - protegido con la clave DH      |
   |                                       |
   |<--- (4) IKE_AUTH ---------------------|
   |      - ID del servidor                |
   |      - AUTH (calculado usando PSK)    |
   |      - protegido con la clave DH      |
   |                                       |
   |==== IKE SA ESTABLECIDA (CANAL SEGURO) |
   |                                       |
   |---- (5) CREATE_CHILD_SA ------------->|
   |      - parámetros IPsec               |
   |                                       |
   |<--- (6) CREATE_CHILD_SA --------------|
   |                                       |
   |==== IPsec SA (ESP ACTIVO) ============|
   |                                       |
   |---- (7) DATOS CIFRADOS (ESP) -------->|
   |<--- (7) DATOS CIFRADOS (ESP) ---------|

```


# Authentification Protocols

Used for verifying the identity of users
![[Pasted image 20260128133224.png]]

