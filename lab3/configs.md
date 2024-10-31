R01.NY:

```
/interface bridge
add name=lobridge
add name=vpn
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
set [ find default-name=ether6 ] disable-running-check=no
/interface vpls
add disabled=no l2mtu=1500 mac-address=02:BD:27:52:DB:8E name=EoMPLS remote-peer=9.9.9.5 vpls-id=100:100
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=9.9.9.2
/interface bridge port
add bridge=vpn interface=ether5
add bridge=vpn interface=EoMPLS
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=9.9.9.2 interface=lobridge network=9.9.9.2
add address=192.168.3.101/30 interface=ether3 network=192.168.3.100
add address=192.168.4.101/30 interface=ether4 network=192.168.4.100
add address=10.10.59.1/29 interface=vpn network=10.10.59.0
add address=192.168.5.101/30 interface=ether5 network=192.168.5.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=9.9.9.2 transport-address=9.9.9.2
/mpls ldp interface
add interface=ether3
add interface=ether4
add interface=ether5
/routing ospf network
add area=backbone network=9.9.9.2/32
add area=backbone network=192.168.3.100/30
add area=backbone network=192.168.4.100/30
/system identity
set name=R01.NY
```

R01.LND:

```
/interface bridge
add name=lobridge
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=9.9.9.3
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=9.9.9.3 interface=lobridge network=9.9.9.3
add address=192.168.4.102/30 interface=ether3 network=192.168.4.100
add address=192.168.8.101/30 interface=ether4 network=192.168.8.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=9.9.9.3 transport-address=9.9.9.3
/mpls ldp interface
add interface=ether3
add interface=ether4
/routing ospf network
add area=backbone network=9.9.9.3/32
add area=backbone network=192.168.4.100/30
add area=backbone network=192.168.8.100/30
/system identity
set name=R01.LND
```


R01.HKI

```
/interface bridge
add name=lobridge
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
set [ find default-name=ether6 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=9.9.9.4
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=9.9.9.4 interface=lobridge network=9.9.9.4
add address=192.168.8.102/30 interface=ether3 network=192.168.8.100
add address=192.168.9.101/30 interface=ether5 network=192.168.9.100
add address=192.168.6.102/30 interface=ether4 network=192.168.6.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=9.9.9.4 transport-address=9.9.9.4
/mpls ldp interface
add interface=ether3
add interface=ether4
add interface=ether5
/routing ospf network
add area=backbone network=9.9.9.4/32
add area=backbone network=192.168.8.100/30
add area=backbone network=192.168.9.100/30
add area=backbone network=192.168.6.100/30
/system identity
set name=R01.HKI
```

R01.SPB:

```
/interface bridge
add name=lobridge
add name=vpn
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
set [ find default-name=ether6 ] disable-running-check=no
/interface vpls
add disabled=no l2mtu=1500 mac-address=02:96:AE:D1:9C:3F name=EoMPLS remote-peer=9.9.9.2 vpls-id=100:100
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=9.9.9.5
/interface bridge port
add bridge=vpn interface=ether5
add bridge=vpn interface=EoMPLS
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=9.9.9.5 interface=lobridge network=9.9.9.5
add address=10.10.0.2/24 interface=vpn network=10.10.0.0
add address=192.168.9.102/30 interface=ether3 network=192.168.9.100
add address=192.168.10.102/30 interface=ether4 network=192.168.10.100
add address=192.168.2.101/30 interface=ether5 network=192.168.2.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=9.9.9.5 transport-address=9.9.9.5
/mpls ldp interface
add interface=ether3
add interface=ether4
add interface=ether5
/routing ospf network
add area=backbone network=9.9.9.5/32
add area=backbone network=192.168.9.100/30
add area=backbone network=192.168.10.100/30
add area=backbone network=192.168.2.100/30
/system identity
set name=R01.SPB
```

R01.MSC:

```
/interface bridge
add name=lobridge
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=9.9.9.6
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=9.9.9.6 interface=lobridge network=9.9.9.6
add address=192.168.7.102/30 interface=ether3 network=192.168.7.100
add address=192.168.10.101/30 interface=ether4 network=192.168.10.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=9.9.9.6 transport-address=9.9.9.6
/mpls ldp interface
add interface=ether3
add interface=ether4
/routing ospf network
add area=backbone network=9.9.9.6/32
add area=backbone network=192.168.7.100/30
add area=backbone network=192.168.10.100/30
/system identity
set name=R01.MSC
```

R01.LBN:

```
/interface bridge
add name=lobridge
/interface ethernet
set [ find default-name=ether1 ] disable-running-check=no
set [ find default-name=ether2 ] disable-running-check=no
set [ find default-name=ether3 ] disable-running-check=no
set [ find default-name=ether4 ] disable-running-check=no
set [ find default-name=ether5 ] disable-running-check=no
set [ find default-name=ether6 ] disable-running-check=no
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] router-id=9.9.9.7
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=9.9.9.7 interface=lobridge network=9.9.9.7
add address=192.168.3.102/30 interface=ether3 network=192.168.3.100
add address=192.168.6.101/30 interface=ether4 network=192.168.6.100
add address=192.168.7.101/30 interface=ether5 network=192.168.7.100
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes lsr-id=9.9.9.7 transport-address=9.9.9.7
/mpls ldp interface
add interface=ether3
add interface=ether4
add interface=ether5
/routing ospf network
add area=backbone network=9.9.9.7/32
add area=backbone network=192.168.3.100/30
add area=backbone network=192.168.6.100/30
add area=backbone network=192.168.7.100/30
/system identity
set name=R01.LBN
```

PC1: 

```
ip add add 10.10.0.50/24 dev eth0
```

SGI-PRISM:

```

```