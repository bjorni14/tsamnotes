# Part 3: TCP Protocol
#### The picture in Figure 1 displays the behaviour of a TCP Reno.
![alt text](https://github.com/Kayui/tsamnotes/blob/master/Main%20Exam%202015/figure1.png "Figure 1")
* Identify the intervals of transmission rounds when TCP slow-start is operating.
    * ANSWER
* Identify the intervals of transmission rounds where TCP congestionavoidance is operating.
    * ANSWER
* After the __16th__ transmission round, is segment loss detected by a triple duplicate ACK or by a time-out? Justify your answer.
    * ANSWER
* After the __22nd__ transmission round, is segment loss detected by a triple duplicate ACK or by a time-out? Justify your answer.
    * ANSWER
* What is the __initial__ value of ssthresh? Justify your answer
    * ANSWER
* What is the value of ssthresh after the __18th__ transmission round? Justify your answer.
    * ANSWER
* What is the value of ssthresh after the __24th__ transmission round? Justify your answer.
    * ANSWER
* During what transmission round is the 70th segment sent?
    * ANSWER
* Assuming a a packet loss is detected after the __26th__ round by the receipt of a triple duplicate ACK, what will be the values of the congestion window size? Justify your answer.
    * ANSWER
* Assuming a packet loss is detected after the __26th__ round by the receipt of a triple duplicate ACK, what will be the values of ssthresh?
    * ANSWER

#### Now, suppose that TCP Tahoe is used instead of TCP Reno. This means, that the congestion window sizes differ from the ones shown in Figure 1.
* Assume that triple duplicate ACKs are received at the __16th__ round. What is the size of the congestion window at the __19th__ round?
    * ANSWER
* Assume that triple duplicate ACKs are received at the __16th__ round. What is the value of ssthresh at the __19th__ round? Justify your answer.
    * ANSWER
* Again, suppose there are triple duplicate ACKs received at the __16th__ round and there is a timeout event at the __22nd__ round. How many packets have been sent out from __17th__ till __22nd__ round, inclusive? Justify your answer.
    * ANSWER
* What is the difference between congestion control and flow control? How are both realised in TCP?
    * ANSWER

