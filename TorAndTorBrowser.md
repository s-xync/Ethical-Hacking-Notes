### Tor And Tor Browser  
Install tor services using `apt-get install tor`  
To check the status of tor services, use `service tor status`  
To stop tor services, use `service tor stop`  
Tor services can be used like this  
`service tor start`  
`proxychains firefox`  
In this case, proxies in the end of the file */etc/proxychains.conf* can be empty  
[Check For DNS LEAKS](www.dnsleaktest.com)  

Download tor browser bundle from *tor project* website  
Save it in a place like **/root**  
I prefer **/root/Applications/**  
`cd Applications`  
`tar -xvf tor*`  
remove the **\*.tar.xz** file  
Keep only the inner directory and remove outer directory  
create a tor user (Do not root user to access tor browser)  
`useradd -m toruser`  
`chsh -s /bin/bash toruser`  
Make him the owner of the folder  
`chown -R toruser tor-browser_en-US`  
To run the Tor Browser, use this command  
`gksu -u toruser   Applications/tor-browser_en-US/Browser/start-tor-browser`  
