### Proxy Chains  
can be accessed using `nano /etc/proxychains.conf`  
There are two options  
1.Strict Chain  
2.Dynamic Chain  
Dynamic Chain is mostly used.  
#### Configuring The File
Just **uncomment dynamic chain** and **comment strict chain** in the file *proxychains.conf*  
Add Proxies at the end of the file  
Mostly used is **socks5**.  
`socks5 <ip> <port>` (space or tab both are okay)  
Proxies can be found for free online.  
It can be used like this  
`proxychains firefox`  
All network traffic for that application will be routed through proxychains.  

[Check For DNS LEAKS](www.dnsleaktest.com)  
