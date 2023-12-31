Based off of
https://forum.qubes-os.org/t/wireguard-vpn-setup/19141  

To clone VPN for another location, clone sys-vpn-location Qube to a new Qube  

Go into this new Qube terminal and show the current VPN connection UUID  

`nmcli connection show`  

Delete the initial vpn UUID 

`nmcli connection delete <UUID>`  

Then import your new location vpn.conf file and run import.    

`nmcli connection import type wireguard file vpn.conf`  

Don't forget to `cat vpn.conf` for the new endpoint and reconfigure the firewall rule to that new endpoint IP  

These all autostart when using, so close them out on each new one, and when you select the location VPN, it will all automatically work. Download a bunch of .conf files from provider into a personal Qube that can copy 1 by 1 into each new cloned VPN Qube.

Great tutorial by solene!
