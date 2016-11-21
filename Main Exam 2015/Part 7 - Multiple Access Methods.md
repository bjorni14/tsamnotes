# Part 7: Multiple Access Methods
#### How does TDMA work?
* Time Division Multiple Access
* A channel access method that allows several users to share the same frequency channel by dividing the signal into different time slots. The users transmit in rapid succession, one after the other, each using it's own time slow. [Source](https://issuu.com/warse/docs/ijeter01352015)

####  How does (pure) ALOHA work?
* If the client or node has data to send, it will send it.
* If the client receives data which doesn't belong to him while he is transmitting, there has been a collision and every node that is transmitting has to try to send again later. 

#### Compare TDMA to ALOHA. What are the advantages and disadvantages?
**TDMA pros:**
* Nodes take turns transmitting to avoid collisions. Less data is lost  

**TDMA cons:**
* TDMA only allows a transfer rate of R/N (Rate of link/Number of nodes).
* Lots of time waiting.

**ALOHA pros:**
* ALOHA allows the node to use the total transfer rate of the link.
* Nodes spend less time waiting (as long as there arent a lot of collisions)  

**ALOHA cons:**
* The chance of a collision is hight if there are many clients.
* A lot af data is lost. (If there is a collision, the data is discarded)

#### Under what circumstances should we prefer ALOHA over TDMA?
* When we have a low chance of two nodes transmitting at the same time.

#### Consider a broadcast channel with N nodes and a transmission rate of R bit s<sup>−1</sup>. Suppose the broadcast channel uses polling (with an additional polling node) for multiple access. Suppose the amount of time from when a node completes transmission until the subsequent node is permitted to transmit (that is, the polling delay) is d<sub>poll</sub>. Suppose that within a polling round, a given node is allowed to transmit at most Q bit. What is the maximum throughput of the broadcast channel?
**NOTE:** not sure if `"with an additional polling node`" changes anything.  

* 1. Calculate the length of the polling round: N(Q/R+d<sub>poll</sub>)
* 2. Calculate the max throughput = N*Q/N(Q/R+d<sub>poll</sub>)
