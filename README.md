# Huawei-MikroTik-Enterprise-Networking-Lab# Huawei–MikroTik Enterprise Networking Lab

## Overview

This project documents the implementation and testing of a small enterprise network using a Huawei S5700 switch and a MikroTik RB951Ui-2HnD router.

The lab demonstrates VLAN segmentation, inter-VLAN routing, DHCP, NAT, firewall configuration, wireless networking, and infrastructure troubleshooting.

## Implementation

- Configured VLANs 10, 20, and 99 on the Huawei switch.
- Configured access and trunk ports for VLAN traffic.
- Implemented a VLAN-aware bridge and VLAN gateway interfaces on MikroTik.
- Configured DHCP services for automatic IP allocation.
- Implemented NAT and firewall policies.
- Configured wireless access for client devices.
- Established a dedicated management VLAN for the Huawei switch.

## Connectivity Testing

| Test | Result |
|---|---|
| VLAN 10 DHCP address allocation | Passed |
| VLAN 20 DHCP address allocation | Passed |
| VLAN 10 gateway connectivity | Passed |
| VLAN 20 gateway connectivity | Passed |
| Inter-VLAN routing | Passed |
| Internet access through NAT | Passed |
| Wireless client connectivity | Passed |
| Huawei management VLAN ping | Passed |
| Huawei SSH remote management | Pending verification |

## Skills Demonstrated

**Network Switching:** VLANs, 802.1Q trunking, access ports, and management VLANs.

**Network Routing:** IP addressing, inter-VLAN routing, DHCP, NAT, and firewall policies.

**Wireless Networking:** Wireless access point configuration, WPA2 security, and DHCP for wireless clients.

**Troubleshooting:** Physical connectivity, Ethernet cabling, DHCP issues, wireless interfaces, and remote management.

## Conclusion

The practical lab demonstrated the deployment and testing of a segmented network using Huawei and MikroTik equipment. It strengthened my understanding of how switching, routing, network services, and security work together in a real infrastructure environment.
