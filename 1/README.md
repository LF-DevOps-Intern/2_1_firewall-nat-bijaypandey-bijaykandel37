
Graphically some settings are applied in VirtualBox, which can be shown in screenshot1, screenshot2 and screenshot3.

The used commands are:
‘ip a’
To edit network scripts:
‘Nano /etc/sysconfig/network-scripts/ifcfg-enp0s3’
‘Nano /etc/sysconfig/network-scripts/ifcfg-enp0s8’

To restart network manager:
‘Systemctl restart NetworkManager.service’

For IP forwarding,
‘cat /etc/sysctl.d/ip_forward.conf >> net.ipv4.ip_forward=1’

To activate it:
‘Sysctl -p /etc/sysctl.d/ip_forward.conf’

Firewall rule:
‘Firewall-cmd --permanent --direct --passthrough ipv4 -t nat -I POSTROUTING -o enp0s3 -j MASQUERADE -s 192.168.1.0/24’

Restart firewall:
‘Systemctl restart firewalld.service’

Implement NAT:
’iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE ‘
iptables -A FORWARD -i eth1 -j ACCEPT ’

And in VM2,
Ping 192.168.1.182






