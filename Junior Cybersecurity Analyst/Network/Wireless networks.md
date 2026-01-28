
Computer networks that doesn't need physical connections. They use RF (radio frequency) to transmit data, also the devices need a wireless adapter to convert this radio waves into data

device --> data --> wireless adapter --> RF --> air --> RF --> wireless adapter --> data --> device 

### Technologies

each network use different wireless technologies

`WLAN` --> WiFi small areas Bandas típicas `2.4 GHz`, `5 GHz`
`WWAN` --> mobile telecomunication technologies like `3G`, `4G LTE`, `5G` thath covers larger areas (moviles con datos)

Communications between devices follows the RFC and they need to be in the same bands `2.4G` or `5G` in a WiFi network

----

`WAP`: connects the wireless network to a wired network and controls access to the network

device(WiFi) <--> WAP (Wireless Access Point) <--> Red cableada/router/internet

modern routers has an integrated WAP

---

### WiFi Connection

When connecting to a router u need to set the `SSID (Service Set Identifier)` and `password` this connection occurs folowing the protocol  [IEEE 802.11] 

1. Association rquest
device --> association request (following IEEE 802.11) --> WAP

**association request**:
- `MAC address` A unique identifier for the device's wireless adapter.
- `SSID` The network name, also known as the `Service Set Identifier` of the WiFi network.
- `Supported data rates` A list of the data rates the device can communicate.
- `Supported channels` A list of the `channels` (frequencies) on which the device can communicate.
- `Supported security protocols` A list of the security protocols that the device is capable of using, such as `WPA2`/`WPA3`.

Then the device configures his wireless adapter to perform the comunication with the WAP. Also there are more protocols: `TCP/IP, DHCP, and WPA2` 

2. Authentification
WiFi networks are configured by default to allow authorized devices to join the network using specific authentication methods. However, these methods can be changed by requiring a password or a unique identifier (such as a MAC address) to identify authorized devices.
`For example WEP is used to authentificate and also encrypt`


[Escuchar RF]
      ↓
[Ver SSID]
      ↓
[Association request]
      ↓
[Association OK]
      ↓
[Security handshake (WPA2)] WEP antes
      ↓
[Wireless adapter configurado]
      ↓
[DHCP → IP]
      ↓
[Internet]

association and authentification

### WEP (Challenge-Response Handshake) protocol

Making a secure channel between device and WAP

|Paso|Quién|Qué ocurre|
|---|---|---|
|1|Client|Sends **association request** to the WAP|
|2|WAP|Sends a **challenge text** (random string)|
|3|Client|Encrypts the challenge using the **shared WEP key** and sends it back|
|4|WAP|Encrypts the same challenge and compares results|
|5|WAP|If they match → authentication successful|
But its not secure

🔑 **En WiFi, la contraseña nunca se envía.**  
WEP intenta demostrarla con challenge–response (mal hecho).  
WPA2/WPA3 la usan para derivar claves, no para enviarla.

### Encryptation

- `WEP`: 
	- `40-bit` or `104-bit` key to encrypt data. 
	- `RC4 cipher` encryption algorithm (not secure)
	- WEP uses a shared key to authentificate and ecrypt (the same key!!!!)
	- ![[Pasted image 20251216185309.png]]
	- easy to brute force
- `WPA`(WPA2, WPA3):
	- more secure authentication methods
		-  [Pre-Shared Key](https://en.wikipedia.org/wiki/Pre-shared_key) (`PSK`) (example: the wifi password)
		- 802.1X authentication server
### Firewalls

built in firewalls in wifi routers 

### Authentification protocols

[Lightweight Extensible Authentication Protocol](https://en.wikipedia.org/wiki/Lightweight_Extensible_Authentication_Protocol) (`LEAP`) and [Protected Extensible Authentication Protocol](https://en.wikipedia.org/wiki/Protected_Extensible_Authentication_Protocol) (`PEAP`) are usually used in conjuction with WEP or WPA.

- `LEAP`: uses a shared key to authentificate and encrypt
- `PEAP`: uses TLS
```
Situación: estás en la universidad

1️⃣ Tú eliges el WiFi:

`UAB-WiFi`

2️⃣ Association (IEEE 802.11)  
👉 Te asocias al WAP (sin acceso real aún)

3️⃣ Empieza 802.1X

`Laptop → “quiero autenticarme”`

4️⃣ El WAP reenvía todo al RADIUS

`WAP → RADIUS → “¿este usuario es válido?”`

5️⃣ Autenticación (EAP)

- Usuario + contraseña
    
- o certificado (EAP-TLS)
    

6️⃣ RADIUS responde

`✔ OK → deja pasar ❌ NO → bloquea`

7️⃣ Se generan claves WiFi  
👉 Ahora sí:

- Se cifra el tráfico
    
- Tienes acceso a la red
```

### TACACS+

admin --> WAP --> TACACS+
TACACS+ is an AAA protocol used to authenticate and authorize administrative access to network devices, not to encrypt or authenticate WiFi clients.
- **Authentication** → ¿quién eres?
    
- **Authorization** → ¿qué puedes hacer?
    
- **Accounting** → ¿qué hiciste?
Several encryption methods may be used to encrypt the authentication request, such as `SSL`/`TLS` or `IPSec`. The specific encryption method used may depend on the configuration of the `TACACS+` server and the capabilities of the WAP

### Disassociation Attack

Aims to disrupt the communication between a WAP and its clients by sending disassociation frames to one or more clients.

The WAP uses disassociation frames to disconnect a client from the network

### Wireless Hardening

- `Disabling broadcasting`: By disabling the broadcasting of the SSID, the WAP will not transmit beacon frames, and the network will not be visible to devices that are not already connected to the network.
- `WiFi Protected Access`: WPA-Personal, designed for home and small business networks, and WPA-Enterprise, designed for larger organizations and uses a centralized authentication server (e.g., RADIUS or TACACS+) to verify the identity of clients.
- `MAC filtering`: allows a WAP to accept or reject connections from specific devices based on their MAC addresses
- `Deploying EAP-TLS`: It uses digital certificates and PKI to verify the identity of clients and establish secure connections