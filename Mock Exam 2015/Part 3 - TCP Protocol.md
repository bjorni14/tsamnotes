# Part 3: TCP Protocol
####  Assume we send 4000 bytes of data. Display the temporal sequence of all TCP segments send from sender to receiver. For each message, indicate the TCP flags set in the header, the sequence number and the ACK number. Assume an MTU of 1500bytes. Do not forget connection establishment and connection tear-down. Assume that there is no congestion and no packet loss. Let the receive window of the receiver be 5000 bytes large.
* ANSWER (Expects a picture)

#### What is the difference between congestion control and flow control? How are both realised in TCP?
* ANSWER

#### The picture in Figure 1 displays the behaviour of a TCP Reno.
![alt text](https://github.com/Kayui/tsamnotes/blob/master/Mock%20Exam%202015/figure1.png "Figure 1")
* Identify the time intervals where TCP slow-start is operating.
    * ANSWER
* Identify the time intervals where TCP congestion-avoidance is operating.
    * ANSWER
* After the __16th__ transmission round, is segment loss detected by a triplicate ACK or by a time-out? Justify your answer.
    * ANSWER
* After the __22nd__ transmission round, is segment loss detected by a triplicate ACK or by a time-out? Justify your answer.
    * ANSWER
* What is the value of ssthresh at the __first__ transmission round? Justify your answer.
    * ANSWER
* What is the value of ssthresh after the __16th__ transmission round? Justify your answer.
    * ANSWER
* What is the value of ssthresh after the __22th__ transmission round? Justify your answer.
    * ANSWER
* Explain why TCP is fair and UDP is not.
    * ANSWER
