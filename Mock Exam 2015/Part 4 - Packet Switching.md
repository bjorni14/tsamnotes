# Part 4: Packet Switching
#### What is the purpose of the ARP protocol?
* __A__ddress __R__esolution __P__rotocol
* ARP has the purpose of converting IP Addresses to Physical Addresses

#### How does the ARP protocol work?
 When an IP addresses MAC address is unknown a broadcast packet is sent that hits all the machines on the network, the machine with the correct IP Address will respond

####  Explain the purpose of a switch: what steps does a switch perform when a packet arrived.
* It stores and forwards Ethernet Frames
* 1. Record incoming link, MAC address of the sending host
* 2. Indexes switch table using MAC destination address
* 3. Run the following pseudocode:
```c
if(entry found for destination) {
    if(destination on segment from which frame arrived) {
        // drop frame
    }
    else{
        // forward frame on interface indicated by entry
    }
}
else{
    // forward on all interfaces except arriving interface
}
```  


####  How does a switching table look like? Explain the purpose of each field.
* ANSWER

#### What is the difference between routing and forwarding?
* ANSWER

####  Define the term Classless Inter-Domain Routing (CIDR)?
* ANSWER

#### Indicate the broadcast address for each of the following subnets.
* 192.168.1.0/24
    * ANSWER
* 192.168.1.0/25
    * ANSWER
* 192.168.128.128/25
    * ANSWER
* To which of the three subnets above does the IP address 192.168.1.222 belong?
    * ANSWER