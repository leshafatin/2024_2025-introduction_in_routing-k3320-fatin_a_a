```
[admin@R01.MSK] > export 
# oct/08/2024 16:46:12 by RouterOS 6.47.9
# software id = 
#
#
#
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip pool
add name=pool_msk ranges=192.168.10.30-192.168.10.100
/ip dhcp-server
add address-pool=pool_msk disabled=no interface=ether5 name=dhcp_msk
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=190.168.10.2/24 interface=ether3 network=190.168.10.0
add address=190.168.30.2/24 interface=ether4 network=190.168.30.0
add address=192.168.10.2/24 interface=ether5 network=192.168.10.0
/ip dhcp-client
add disabled=no interface=ether1
/ip dhcp-server network
add address=192.168.10.0/24 dns-server=8.8.8.8 gateway=192.168.10.2
/ip route
add distance=1 dst-address=192.168.20.0/24 gateway=190.168.10.3
add distance=1 dst-address=192.168.30.0/24 gateway=190.168.30.3
/system identity
set name=R01.MSK
```


```
[admin@R02.BRL] > export 
# oct/08/2024 17:01:24 by RouterOS 6.47.9
# software id = 
#
#
#
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip pool
add name=pool_brl ranges=192.168.20.30-192.168.20.100
/ip dhcp-server
add address-pool=pool_brl disabled=no interface=ether5 name=dhcp_brl
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=190.168.10.3/24 interface=ether3 network=190.168.10.0
add address=190.168.20.2/24 interface=ether4 network=190.168.20.0
add address=192.168.20.2/24 interface=ether5 network=192.168.20.0
/ip dhcp-client
add disabled=no interface=ether1
/ip dhcp-server network
add address=192.168.20.0/24 dns-server=8.8.8.8 gateway=192.168.20.2
/ip route
add distance=1 dst-address=192.168.10.0/24 gateway=190.168.10.2
add distance=1 dst-address=192.168.30.0/24 gateway=190.168.20.3
/system identity
set name=R02.BRL
```


```
[admin@R03.FRT] > export
# oct/08/2024 18:17:58 by RouterOS 6.47.9
# software id = 
#
#
#
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip pool
add name=pool_frt ranges=192.168.30.30-192.168.30.100
/ip dhcp-server
add address-pool=pool_frt disabled=no interface=ether5 name=dhcp_frt
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=190.168.20.3/24 interface=ether3 network=190.168.20.0
add address=190.168.30.3/24 interface=ether4 network=190.168.30.0
add address=192.168.30.2/24 interface=ether5 network=192.168.30.0
/ip dhcp-client
add disabled=no interface=ether1
/ip dhcp-server network
add address=192.168.30.0/24 dns-server=8.8.8.8 gateway=192.168.30.2
/ip route
add distance=1 dst-address=192.168.10.0/24 gateway=190.168.30.2
add distance=1 dst-address=192.168.20.0/24 gateway=190.168.20.2
/system identity
set name=R03.FRT
```