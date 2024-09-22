## R01

```
[admin@R01] > export 
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
/interface vlan
add interface=ether3 name=vlan10 vlan-id=10
add interface=ether3 name=vlan20 vlan-id=20
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip pool
add name=pool_vlan10 ranges=10.10.10.10-10.10.10.100
add name=pool_vlan20 ranges=10.10.20.10-10.10.20.100
/ip dhcp-server
add address-pool=pool_vlan10 disabled=no interface=vlan10 name=dhcp_vlan10
add address-pool=pool_vlan20 disabled=no interface=vlan20 name=dhcp_vlan20
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.10.10.2/24 interface=vlan10 network=10.10.10.0
add address=10.10.20.2/24 interface=vlan20 network=10.10.20.0
/ip dhcp-client
add disabled=no interface=ether1
/ip dhcp-server network
add address=10.10.10.0/24 dns-server=8.8.8.8,8.8.4.4 gateway=10.10.10.2
add address=10.10.20.0/24 dns-server=8.8.8.8,8.8.4.4 gateway=10.10.20.2
/system identity
set name=R01
```

## SW01.01
```
/interface bridge
add name=br_vlan10
add name=br_vlan20
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface vlan
add interface=ether3 name=vlan10 vlan-id=10
add interface=ether4 name=vlan10_2 vlan-id=10
add interface=ether3 name=vlan20 vlan-id=20
add interface=ether5 name=vlan20_2 vlan-id=20
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/interface bridge port
add bridge=br_vlan10 interface=vlan10
add bridge=br_vlan10 interface=vlan10_2
add bridge=br_vlan20 interface=vlan20
add bridge=br_vlan20 interface=vlan20_2
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
/ip dhcp-client
add disabled=no interface=ether1
add disabled=no interface=br_vlan10
add disabled=no interface=br_vlan20
/system identity
set name=SW01.01
```

## SW02.01

```
/interface bridge
add name=br_vlan10
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
/interface vlan
add interface=ether3 name=vlan10 vlan-id=10
add interface=ether4 name=vlan10_2 vlan-id=10
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/interface bridge port
add bridge=br_vlan10 interface=vlan10
add bridge=br_vlan10 interface=vlan10_2
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
/ip dhcp-client
add disabled=no interface=ether1
add disabled=no interface=br_vlan10
/system identity
set name=SW02.01
```


## SW02.02

```
/interface bridge
add name=br_vlan20
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
/interface vlan
add interface=ether3 name=vlan20 vlan-id=20
add interface=ether4 name=vlan20_2 vlan-id=20
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/interface bridge port
add bridge=br_vlan20 interface=vlan20
add bridge=br_vlan20 interface=vlan20_2
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
/ip dhcp-client
add disabled=no interface=ether1
add disabled=no interface=br_vlan20
/system identity
set name=SW02.02
```