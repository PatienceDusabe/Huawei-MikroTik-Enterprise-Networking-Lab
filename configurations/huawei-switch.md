# Huawei S5700 configuration notes

## VLAN plan
- VLAN 10 — Administration, access port GE0/0/1
- VLAN 20 — Employees, access port GE0/0/2
- VLAN 99 — Management, access port GE0/0/3
- GE0/0/24 — trunk allowing VLANs 10 and 20

## Illustrative configuration excerpts
These are **reference snippets**, not a verified full export. Confirm actual device port names and existing settings before applying.

```text
system-view
sysname SW-LAB
vlan batch 10 20 99
interface GigabitEthernet 0/0/1
 port link-type access
 port default vlan 10
 quit
interface GigabitEthernet 0/0/2
 port link-type access
 port default vlan 20
 quit
interface GigabitEthernet 0/0/3
 port link-type access
 port default vlan 99
 undo shutdown
 quit
interface GigabitEthernet 0/0/24
 port link-type trunk
 port trunk allow-pass vlan 10 20
 quit
interface Vlanif 99
 ip address 192.168.50.2 255.255.255.0
 undo shutdown
 quit
return
save
```

## Verification commands
```text
display vlan
display port vlan
display ip interface brief
display interface brief
display ssh server status
display acl 2002
```

## Management status
- Ping 192.168.50.2 from laptop configured as 192.168.50.10/24: passed.
- SSH remote login: failed/timed out. VTY configuration showed `acl 2002 inbound`; inspect permitted sources before edits.
- Do not publish SSH user passwords or cryptographic material.
