# Part 3: TCP Protocol
####  Assume we send 4000 bytes of data. Display the temporal sequence of all TCP segments send from sender to receiver. For each message, indicate the TCP flags set in the header, the sequence number and the ACK number. Assume an MTU of 1500bytes. Do not forget connection establishment and connection tear-down. Assume that there is no congestion and no packet loss. Let the receive window of the receiver be 5000 bytes large.
* ANSWER (Expects a picture)

#### What is the difference between congestion control and flow control? How are both realised in TCP?
* Flow control: Receiver side. Ensures sender can only send what the receiver can handle. In flow control the sender maintains a variable called rwnd. It gives the sender an idea of how much space is in the receivers buffer. It is calculated like this: rwnd = RvcBuffer - (LastBiteSent - LastByteAcked)
* Congestion control: Method of ensuring everyone on the network has a "fair" amount of access to netowrk resources
* 

#### The picture in Figure 1 displays the behaviour of a TCP Reno.
![alt text](https://github.com/Kayui/tsamnotes/blob/master/Mock%20Exam%202015/figure1.png "Figure 1")
* Identify the time intervals where TCP slow-start is operating.
    * 1-5 and 22-24
* Identify the time intervals where TCP congestion-avoidance is operating.
    * 5-15 and 16-21
* After the __16th__ transmission round, is segment loss detected by a triplicate ACK or by a time-out? Justify your answer.
    * Tripple ACK, as the cwnd size is devided by 2 and not decreaced to 1MSS as when a loss is detected.
* After the __22nd__ transmission round, is segment loss detected by a triplicate ACK or by a time-out? Justify your answer.
    * A time-out is experienced as the cwnd size is set to 1MSS.
* What is the value of ssthresh at the __first__ transmission round? Justify your answer.
    * 32, thats when slow start stops
* What is the value of ssthresh after the __16th__ transmission round? Justify your answer.
    * 21 as its cwnd/2
* What is the value of ssthresh after the __22th__ transmission round? Justify your answer.
    * its 13 as its cwnd/2
* Explain why TCP is fair and UDP is not.
    * ANSWER
