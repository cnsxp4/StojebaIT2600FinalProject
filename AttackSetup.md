# Attack Machine Setup
This is a separate virtual machine with an IP Address of _192.168.166.202_

1. To start, we will use 'nmap' to search the target machine to find an open port.  'nmap 192.168.166.201'
![Attack1](https://github.com/cnsxp4/StojebaIT2600FinalProject/blob/master/Attack1.png)

Nmap returns that port 80/tcp is open. This makes sense beacuse the target machin is running and HTTP server

2. The next step is to get ready to run the Metasploit console.  The first step is to ensure that postgresql is running
  '# /etc/init.d/postgresqlstatus'
  
  '#/etc/init.d/postgresqlstart'
  
  This starts the postgresql services.  Next we have to initialize the Metasploit database.
  
  '# msfdbinit'
  
  Once that is conplete, we can execute the Metasploit console
  
  '# msfconsole'
  
  ![Attack2](https://github.com/cnsxp4/StojebaIT2600FinalProject/blob/master/Attack2.png)
  
 3. Now we can prepare Metaspliot to carry out our SYN Flood Attack.
 
  First, we select the auxiliary that will run the attack.
  'use auxiliary/dos/tcp/synfloof'
  
  Next set the target host's IP address.
  
  'set RHOSTS 192.168.166.201'
  
  The default target port should be 80, however it can be set using the following.
  
  'set RPORT 80'
  
  Once all the information is input, the attack can be executed with this command.
  
  'exploit'
  
  3. Durring the attack, Wireshark can be used to view how many packets have been sent to the target.
  
  ![Attack3](https://github.com/cnsxp4/StojebaIT2600FinalProject/blob/master/Attack3.png)
  
  The highlighted portion shows that we have sent 119,591 packets to the target machine at this point in time
  
  Similarly, if we want to see how this is effecting the host machine, we can attempt to connect to the host site using the host's IP address.  The site should be slow to load or inaccessible entirely.  On the host machine, we can load the system info application and look at the network load
  
  ![Attack4](https://github.com/cnsxp4/StojebaIT2600FinalProject/blob/master/Attack4.png)
 
  
