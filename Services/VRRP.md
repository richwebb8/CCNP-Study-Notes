# VRRP
## What is VRRP?
- Virtual Router Redundancy Protocol
- An FHRP
- Not Cisco Proprietary
- Very similar to HSP except:
    - Master and backup routers
    - Preemption enabled by default
    - Virtual MAC 000.5e00.01xx where xx is the group ID in hex
    - Multicast address 224.0.0.18
## VRRP Versions
- VRRPv2: IPv4
- VRRPv3: IPv4 and IPv6