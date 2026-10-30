# MikroTik RB951Ui-2HnD configuration notes

Use WinBox GUI; these are notes for review, not a device export.

## Port roles
| Interface | Function |
|---|---|
| ether1 | WAN (upstream connectivity not yet verified) |
| ether2 | 802.1Q trunk to Huawei |
| ether3 | Dedicated management, if current setup retains it |
| wlan1 | Wireless AP for users (validation pending) |

## Bridge and VLANs
- `bridge-LAN` VLAN-aware bridge.
- `ether2` is tagged for VLANs 10 and 20.
- Bridge itself is tagged member for VLANs 10 and 20 (CPU/routing).
- VLAN interfaces `vlan10-admin` and `vlan20-employees` are on `bridge-LAN`.
- Gateway IPs: 192.168.10.1/24 and 192.168.20.1/24.

## DHCP and WLAN
- VLAN 10 pool: 192.168.10.100–192.168.10.200.
- VLAN 20 pool: 192.168.20.100–192.168.20.200.
- Wi-Fi AP SSID proposed: LAB-WIFI; wlan1 gateway 192.168.40.1/24 and pool 192.168.40.100–200.
- Check the actual state in WinBox; successful client leases are not yet documented.

## NAT, firewall and routes
- Masquerade for 192.168.10.0/24, 192.168.20.0/24, and 192.168.40.0/24 on **actual WAN interface**.
- Configure stateful `input` and `forward` filtering. Restrict management and unsolicited WAN access.
- Directly connected routes appear when gateway addresses are configured and interfaces become operational.
- Do not claim internet or inter-VLAN access is verified until client tests pass.

## GUI verification sequence
1. Interfaces / Bridge / Bridge VLANs
2. IP → Addresses
3. IP → DHCP Server → Servers, Networks, Leases
4. IP → Routes
5. IP → Firewall → Filter Rules, NAT
6. Wireless → Interfaces, Security Profiles, Registration
7. Tools → Ping; test from end-user devices

## Security
Never upload RouterOS `.backup` files or unredacted `/export` output. Exports can include sensitive data and device identifiers. Sanitize screenshots and snippets.
