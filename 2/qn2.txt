In this question, the used commands are:



a.
For verification of installation of firewall:
‘Firewall-cmd -V’

To check the status of firewall:
‘Systemctl status firewalld’



b.
To see the implemented firewall rules:
‘Firewall-cmd --list-all’

To block certain IP or range of IP in the firewall:
‘Firewall-cmd --permanent --add-rich-rule=” rule family= ‘ipv4’ source address=xxx.xxx.xxx.xxx/xx reject ”’
xxx.xxx.xxx.xxx/xx denotes the IP range which you want to block or reject.
To block the network, we can simply use ‘block’ in place of ‘reject’.



c.
To allow desired services(https,http and ssh) in firewall:
Firewall-cmd --add-service=https
Firewall-cmd --add-service=http
Firewall-cmd --add-service=ssh



d.
To remove the services:
‘Firewall-cmd --remove-service=https’
‘Firewall-cmd --remove-service=http’
It will remove the previously added services http and https.

