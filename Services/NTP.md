# NTP
## What is NTP?
- Network Time Protocol
- UDP
- Port 123
## What are Stratums?
- Identify the accuracy of a time source
- Stratum 1 server connect directly to an authoritive time source
- Stratum 2 server connects to a Stratum 1 server
- Stratum 3 server connects to a Stratus 2 server ... etc
- A client will choose the lowest stratum device
## NTP Server Configuration
<pre>
(config)# <b>ntp server</b> ip-address [<b>prefer</b>] [<b>source</b> interface-id]
</pre>
## What are NTP Peers?
- Multiple NTP peers act as NTP clients and servers to eachother and blend their time
## NTP Peer Configuration
<pre>
(config)# <b>ntp peer</b> ip-address
</pre>
## Verifying NTP
<pre>
(config)# <b>show ntp status</b>
</pre>
<pre>
(config)# <b>show ntp associations</b>
</pre>