# Part 1: Layer Model
#### What are the five layers in the Internet protocol stack? What are the principal responsibilities of each of these layers?
* Application Layer
    * Supporting network applications
* Transport Layer
    * Process-process data transfer
* Network Layer
    * Routing datagrams from source to destination
* Link Layer
    * Data transfer between neighboring network elements
* Physical Layer
    * Transfer bits on a wire

#### For each of the following protocols, indicate the layer it belongs to:
* DNS: 
    * Application Layer ( [source](https://en.wikipedia.org/wiki/List_of_network_protocols_(OSI_model)) )
* UPD:
    * Transport Layer ( [source](https://en.wikipedia.org/wiki/List_of_network_protocols_(OSI_model)) )
* IP: 
    * Network Layer
* OSPF:
    * Network Layer ( [source](https://en.wikipedia.org/wiki/List_of_network_protocols_(OSI_model)) )
* CSMA:
    * Physical Layer ( [source](http://www.linfo.org/csma_cd.html) )

#### Indicate the layer we use logical addresses and what they are called.
* On what layer do we use logical addresses?
    * Network Layer
* How do we call logical addresses?
    * IP address
* On what layer do we use physical addresses?
    * Link Layer
* How do we call physical addresses?
    * MAC address

#### Suppose Host A wants to send a large file to Host B. The path from Host A to Host B has three links, of rates R<sub>1</sub> = 500 kbps, R<sub>2</sub> = 2 Mbps, R<sub>3</sub> = 1 Mbps
* i. Assuming no other traffic in the network, what is the throughput for the file transfer?
    * 500kbps
* ii. Suppose the file is 4 million bytes. Dividing the file size by the throughput, roughly how long will it take to transfer the file to Host B?
    * ( 4`*`10<sup>6</sup>`*`8 )/( 500`*`10<sup>3</sup> ) = 64 seconds
* Repeat i and ii, but now with R<sub>2</sub> reduced to 100 kbps.
    * i: 100kbps
    * ii: ( 4`*`10<sup>6</sup>`*`8 )/( 100`*`10<sup>3</sup> ) = 320 seconds

#### Suppose there is a 1 Mbit/s microwave link between a geostationary satellite and its base station on Earth (distance of about 36 Mm). Every 30 seconds, the satellite takes a digital photo and sends it to the base station. Assume a propagation speed of 240 Mm/s.
* What is the propagation delay of the link?
    * __d<sub>prop</sub>__ = distance / speed = 36 / 240 = 0.15 seconds
* What is the bandwidth-delay product, R ⋅ d<sub>prop</sub>?
    * __d<sub>prop</sub>__ `*` R = 0.15 `*` 10<sup>6</sup> = 150000 = 1.5`*`10<sup>5</sup> bits
* Let x denote the size of the photo. What is the minimum value of x for the microwave link to be continuously transmitting?
    * There is a 30 second window between transmissions
    * X = 30 seconds `*` 1Mbit/s = 30 `*` 10<sup>6</sup> = 30 000 000 bits = 30Mb
