

`ifconfig -a` --> interface configuration -all

for configuring network interface (commonly ip, mask, mac...)
hay distintas interfaces de red: 

```
ifconfig -a
ens3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 94.237.57.195  netmask 255.255.252.0  broadcast 94.237.59.255
        inet6 fe80::a4ba:3bff:fe08:6a73  prefixlen 64  scopeid 0x20<link>
        ether a6:ba:3b:08:6a:73  txqueuelen 1000  (Ethernet)
        RX packets 8571  bytes 3099033 (2.9 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 7014  bytes 17448728 (16.6 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 12512  bytes 17373540 (16.5 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 12512  bytes 17373540 (16.5 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

tun0: flags=4305<UP,POINTOPOINT,RUNNING,NOARP,MULTICAST>  mtu 1500
        inet 10.10.15.146  netmask 255.255.254.0  destination 10.10.15.146
        inet6 fe80::e7e6:b5fb:c938:cd2c  prefixlen 64  scopeid 0x20<link>
        inet6 dead:beef:2::1190  prefixlen 64  scopeid 0x0<global>
        unspec 00-00-00-00-00-00-00-00-00-00-00-00-00-00-00-00  txqueuelen 500  (UNSPEC)
        RX packets 79  bytes 6636 (6.4 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 85  bytes 6960 (6.7 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

```


`netstat -tulnp4` --> estado de la red (network connections, routing tables, interface statistics)
-t(tcp)u(udp)l(loopback)n(ip:port)p(ports)4(ipv4)

```
user@user-NBLB-WAX9N:~$ sudo netstat -tulnp4
[sudo] password for user:             
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 127.0.0.1:36315         0.0.0.0:*               LISTEN      823/confighandler   
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      732/systemd-resolve 
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      2810/cupsd          
tcp        0      0 127.0.0.1:6463          0.0.0.0:*               LISTEN      3321/exe            
tcp        0      0 127.0.0.1:6379          0.0.0.0:*               LISTEN      921/redis-server 12 
tcp        0      0 127.0.0.1:5432          0.0.0.0:*               LISTEN      986/postgres        
udp        0      0 0.0.0.0:5353            0.0.0.0:*                           791/avahi-daemon: r 
udp        0      0 0.0.0.0:38316           0.0.0.0:*                           791/avahi-daemon: r 
udp        0      0 127.0.0.53:53           0.0.0.0:*                           732/systemd-resolve 
user@user-NBLB-WAX9N:~$ 
```

sin la n `netstat -tulp4` sera hostname:service


`ip route get 10.129.233.197` muestra la ruta que hace para llegar a  ip

`ping -c 4 10.129.233.197 ` mandamos pings para ver si llega la conexion (ICMP echo requests)


