# Part 4: Packet Switching
#### What is the purpose of the ARP protocol?
* Address Resolution Protocol
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
* It has 3 fields
    * MAC address of host
    * Interface of host
    * time stamp

#### What is the difference between routing and forwarding?
* Routing is the act of finding a path for a packet from sender to receiver
* Forwarding is the act of sending the packer through said route

####  Define the term Classless Inter-Domain Routing (CIDR)?
* Also called Supernetting
* A method to allow more flexible allocation of IP Addresses

#### Indicate the broadcast address for each of the following subnets.
* NOTE: [This was answered nicely on piazza](https://piazza.com/class/irhlughcpnt1q4?cid=304)
* 192.168.1.0/24
    * Calculation with explanation:
        * 192.168.1.0 in binary: 
            * 11000000 10101000 00000001 00000000
        * 24 in binary with the same number of bits is the subnet mask:
            * 11111111 11111111 11111111 00000000
        * Next we negate the subnet mask:
            * 00000000 00000000 00000000 11111111
        * Then we or ( | ) the negated subnet mask and the binary representation of the ip
            *   11000000 10101000 00000001 00000000
            * | 00000000 00000000 00000000 11111111
            * = 11000000 10101000 00000001 11111111
        * Finally we convert the result back to ip format
            * 192.168.1.255
        * Profit!

* 192.168.1.0/25
    * Calculation with explanation:
        * 192.168.1.0 in binary: 
            * 11000000 10101000 00000001 00000000
        * converting 24 to a subnet mask means doing 24 1's from left to right 
            * 11111111 11111111 11111111 00000000
        * Next we negate the subnet mask:
            * 00000000 00000000 00000000 11111111
        * Then we or ( | ) the negated subnet mask and the binary representation of the ip
            *   11000000 10101000 00000001 00000000
            * | 00000000 00000000 00000000 11111111
            * = 11000000 10101000 00000001 11111111
        * Finally we convert the result back to ip format
            * 192.168.1.255
            
* 192.168.128.128/25
    * ANSWER
* To which of the three subnets above does the IP address 192.168.1.222 belong?
    * ANSWER
