### Mac Changer
From the first jump, mac address is not shared. i.e laptops mac address stops at router.  
We can change mac address using **macchanger**

`macchanger --help`  
`macchanger -s eth0`  
mac address of ethernet card is showed


add these lines so that the changes stay even after restarting network-manager.  
`nano /etc/NetworkManager/NetworkManager.conf`  
under connection section add these lines  
`[connection]`  
`ethernet.cloned-mac-address=preserve`  
`wifi.cloned-mac-address=preserve`  
The values can be `random` and `preserve`  
save and close the file  
`service network-manager stop`  
`ifconfig eth0 down`  
`macchanger -r eth0`  
`ifconfig eth0 up`  
`service network-manager start`  
