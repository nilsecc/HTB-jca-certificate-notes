
A device or service in the middle of a connection taking the role of a **mediator**. The mediator/proxy has the ability to read the traffic (this differe a mediator from a gateway).

They operate at layer 7 of the OSI model (Application). Also they have the hability to decrypt and encrypt again the traffic to analyze.

### Types of Proxies

#### `Dedicated Proxy/Forward Proxy`: 
client --> proxy --> service
- acces control
- content filtering
- logging (keep loggs)
- caching
- anonymaty (shows the proxy ip not the client)

security --> if a client is infected with malware, probably the malware won't be programmed to send the traffic to a proxy (in the case of a coprorate that has a forward proxy for the employees to acces the internet and services) so wouldn't be able to make communications with the exterior. But he can try through DNS consults, other protocols like icmp not protected in the egree proxy rules, etc.
![[Pasted image 20251210210340.png]]

#### `Reverse Proxy`: 
server <-- proxy <-- client
- Sits in front of servers and handles **incoming traffic** from the Internet.
- Clients connect to the **reverse proxy**, not to the real server.
- Protects and hides the internal infrastructure
- The real server is **not exposed** to the Internet.
- Attackers cannot directly target backend services or vulnerable ports.
- Reverse proxies can inspect HTTP/S traffic.
- Detect and block attacks such as **SQL injection, XSS, RCE, directory traversal**, etc.
- Examples: Cloudflare WAF, ModSecurity with the OWASP CRS.
- Stops high-volume attacks before they reach the backend.
- Mitigates brute-force attempts and request floods.

Also attacker use reverse proxies!!! (search info)

![[Pasted image 20251210212252.png]]

#### `(Non-) Transparent Proxy`: 

- Clients **must be explicitly configured** to use the proxy.
- Applications need a proxy setting (host, port, authentication).
- Without this configuration, the client has **no Internet access**.
- Allows granular **per-user access control**, **authentication**, **policy enforcement**, and **logging**.
- Easy to manage in environments where clients are under administrative control (corporate laptops).
- Applications that obey system proxy settings (Chrome, Edge, IE via WinSock) can be forced through it.
- Using direct IP connections
- Using non-standard port.
- Using their own networking libraries that ignore system proxy settings (e.g., custom HTTP stack).