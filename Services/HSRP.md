# HSRP
## What is HSRP?
- Hot Standby Routing Protocol
- An FHRP
- Cisco proprietary
- Active and standby routers
- VIP and virtual MAC address configured on each HSRP-enabled interface
that belongs to the same HSRP group
## HSRP Active Router Election
- HSRP election selects the router with
the highest priority (default 100) to be active
- If a tie occurs the router with the highest IP address becomes active
## Preemtion
- Not enabled by default
## Failover
- Active router sends periodic hello messages
- If a hello is not recieved by the standby router(s), re-election occurs
## Differences between Version 1 & 2
|                   | Version 1                                                                  | Version 2                        |
| ----------------- |----------------------------------------------------------------------------| -------------------------------- |
| Timers            | Does not support milisecond timers                                         | Supports milisecond timers       |
| Group Range       | 0-255                                                                      | 0-4095                           |
| Multicast Address | 224.0.0.2                                                                  | 224.0.0.102                      |
| MAC Address Range | 0000.0C07.ACxy, where xy is a hex value representing the HSRP group number | 0000.0C9F.F000 to 0000.0C9F.FFFF |
## Configuration
- Configure the VIP:
<pre>
(config-if)# <b>standby</b> instance-id <b>ip</b> vip-address
</pre>
- (Optional) Configure preemption:
<pre>
(config-if)# <b>standby</b> instance-id <b>preempt</b>
</pre>
- (Optional) Configure priority:
<pre>
(config-if)# <b>standby</b> instance-id <b>priority</b> priority
</pre>
- (Optional) Configure the virtual MAC:
<pre>
(config-if)# <b>standby</b> instance-id <b>mac-address</b> mac-address
</pre>
- (Optional) Configure the timers:
<pre>
(config-if)# <b>standby</b> instance-id <b>timers</b> {seconds | <b>msec</b> milliseconds}
</pre>
- (Optional) Configure authentication:
<pre>
(config-if)# <b>standby</b> instance-id <b>authentication</b> {text-password | <b>text</b> text-password | <b>md5 key-chain</b> key-chain | <b>key-string</b> key-string}
</pre>
## Verification
<pre>
# <b>show standby [brief]</b>
</pre>