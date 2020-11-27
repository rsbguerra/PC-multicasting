## PC config
### Laptop 0
```
IPv4: 192.168.99.2
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.99.1
```
### Laptop 2
```
IPv4: 192.168.99.3
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.99.1
```
### Laptop 3
```
IPv4: 192.168.99.4
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.99.1
```
### Laptop 4
```
IPv4: 192.168.99.5
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.99.1
```
## Switch

### Config Vlan
```
Switch>en
Switch#conf t

Switch(config)#vlan 99
Switch(config-vlan)#name vlan99
Switch(config-vlan)#exit
Switch(config)#interface FastEthernet0/2
Switch(config-if)#switchport access vlan 99
Switch(config-if)#exit

Switch(config)#interface FastEthernet0/3
Switch(config-if)#switchport access vlan 99
Switch(config-if)#exit

Switch(config)#interface FastEthernet0/4
Switch(config-if)#switchport access vlan 99
Switch(config-if)#exit

Switch(config)#interface FastEthernet0/5
Switch(config-if)#switchport access vlan 99
Switch(config-if)#exit

Switch(config)#interface FastEthernet0/1
Switch(config-if)#switchport mode trunk
Switch(config-if)#switchport trunk allowed vlan 99
```

## Router
### Config Vlan

```
Router>enable

Router#configure terminal
Router(config)#interface GigabitEthernet0/0
Router(config-if)#no shutdown

R1(config)#int g0/0.99
Router(config-subif)#encapsulation dot1Q 99
Router(config-subif)#ip address 192.168.99.1 255.255.255.0
```