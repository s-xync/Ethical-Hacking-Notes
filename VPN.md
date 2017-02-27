### VPN
Plugins for VPN support  
`apt-get install network-manager-openvpn network-manager-openvpn-gnome network-manager-pptp network-manager-pptp-gnome network-manager-strongswan network-manager-vpnc network-manager-vpnc-gnome`  
`service network-manager restart`  
Download openvpn service bundles from [vpnbook](www.vpnbook.com)  
Extract the bundles and put them anywhere like in **/root/Applications/**  
to run a file, for example **tcp443.ovpn**  
`openvpn --config tcp443.ovpn`  
Username and Password can be in [vpnbook](www.vpnbook.com) at the section where service bundles were downloaded.  

This is not enough for leaktest. Here our DNS searches happen from our router. To bypass that, we use opendns.  
The ipaddresses are..  
1.**208.67.222.222**  
2.**208.67.220.220**  
OpenVPN is registered to openDNS through VPNbook.  
So we have to do this..  
`nano /etc/resolv.conf`  
Comment the routers ipaddress line.  
Add these two lines..  
`nameserver 208.67.222.222`  
`nameserver 208.67.220.220`  
**Do not** restart the network-manager.  
This has to be done **always** whenever we want to use it.
