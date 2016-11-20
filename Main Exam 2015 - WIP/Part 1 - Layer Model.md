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
* HTTP: 
    * ANSWER
* TCP:
    * ANSWER
* IP: 
    * Network Layer
* RIP:
    * ANSWER
* ALOHA:
    * ANSWER

#### Suppose you would like to urgently deliver 20 TB of data from Boston to Los Angeles. You have available a 100 MB s<sup>−1</sup> dedicated link for data transfer. Would you prefer to transmit the data via this link or instead use FedEx overnight delivery? Explain.
* ANSWER

/*******************************
#### Suppose there is a 10 Mbit/s microwave link between a geostationary satellite and its base station on Earth (distance of about 36 Mm). Every minute, the satellite takes a digital photo and sends it to the base station. Assume a propagation speed of 240 Mm/s.
* What is the propagation delay of the link?
    * __d<sub>prop</sub>__ = distance / speed = 36 / 240 = 0.15 seconds
* What is the bandwidth-delay product, R ⋅ d<sub>prop</sub>?
    * __d<sub>prop</sub>__ `*` R = 0.15 `*` 10<sup>7</sup> = 150000 = 1.5`*`10<sup>6</sup> bits
* Let x denote the size of the photo. What is the minimum value of x for the microwave link to be continuously transmitting?
    * There is a 60 second window between transmissions
    * X = 60 seconds `*` 10Mbit/s = 60 `*` 10<sup>7</sup> = 60 000 0000 bits = 600Mb
