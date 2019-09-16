# Fail2Ban-Permanent-Ban

This is the 'iptables-multiport.config' file to add a permanent ban rule list to iptables while running / start / stop fail2ban service.

First, check the banaction currently used (you need that, to modify the correct actionfile afterwards)
'/etc/fail2ban/jail.local'

ACTIONS

banaction = iptables-multiport


Second: the file iptables-multiport.config needs to be uploaded to the  '/etc/fail2ban/action.d/' directory 

Every time a IP is banned from Fail2Ban, iptables-multiport.config add a new iptable rule to drop that IP.

Every time fail2ban is stopped, it flush iptables f2b chain rules

Every time Fail2Ban is started, it add a iptables f2b chain rule for every ip listed in the file '/etc/fail2ban/ip.blocklist'

Enjoy

Original: https://looke.ch/wp/list-based-permanent-bans-with-fail2ban
