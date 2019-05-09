# Host Countermeasures (mod_evasive)

Mod_evasive is a utility that is available for Apache2 that allows the host to designate how many requests can be made by the user within a givin amount of time.  If that limit is reached, that user will be added to a blocked list and will be denied access to the server for a determined amount of time.

1.  To install mod_evasive, run the following commands

  `apt-get install apache2-util1`
  
  `apt-get install libapache2-mod-evasive`
  
  2. After install is complete navigate to the mod_evasive config file
  
  `cd /etc/apache2/mods-enabled/evasive.conf`
  
  `vim evasive.conf`
  
  Edit the config file however you choose, here is a description of what each varriable means.
  
 ![Counter1](https://github.com/cnsxp4/StojebaIT2600FinalProject/blob/master/Counter1.png)
 
2.  Restart the Apache2 Server so that the changes can be implemented 
   `service apache2 start`
   
3. Carry out the DoS attack once again with mod_evasive enabled.  You should notice that the webpage does not slow as heavily as it did in the prior attack.  To ensure that the attack machine's IP address is being blocked, search the host's IP address in a web browser
You should see and error message similar to this:

 ![Counter2](https://github.com/cnsxp4/StojebaIT2600FinalProject/blob/master/Counter2.png)
 
 Something to remeber is that the Host's network load will still be high and performance will suffer because mod_evasive needs to compare each packet's IP Address to that of the incoming packets.  
 
 This concludes the tutorial, feel free to try different settings and exploits against the server.
  
 [Back to readme](README.md)

  
  
