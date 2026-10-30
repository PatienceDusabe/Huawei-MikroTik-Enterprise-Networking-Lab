# Troubleshooting and lessons learned

| Issue | Diagnosis / outcome | Lesson |
|---|---|---|
| Laptop unable to reach MikroTik reliably | Faulty Ethernet cable was identified during testing | Verify physical link and cable before changing IP settings |
| Confusion between console and Ethernet connections | USB-to-RJ45 console cable does not function as Ethernet NIC | Use console for CLI management on supported ports, Ethernet for normal traffic |
| MikroTik wireless DHCP client `stopped` | wlan1 not associated; scan detected APs, but stable uplink not verified | Confirm link state and association before troubleshooting DHCP/NAT |
| Huawei management VLAN ping failure | Interface/link and laptop static IP needed checking; ping later passed | Check VLAN membership, port/link state and addressing first |
| Huawei SSH timeout | TCP 22 failed while ping passed; VTY had inbound ACL 2002 | Separate IP connectivity from management service and ACL policy |
| Connected VLAN routes | MikroTik generates connected routes for configured active VLAN networks | No static route is needed between two directly connected subnets |

## Evidence still needed
- Configured VLAN and trunk output
- VLAN 10 and VLAN 20 DHCP leases
- Gateway and cross-VLAN tests
- WAN ping and DNS test
- Wi-Fi phone DHCP and internet test
- SSH resolution or precise pending issue
