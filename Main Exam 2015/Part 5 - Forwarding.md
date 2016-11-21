# Part 5: Forwarding
#### Consider a datagram network using 32-bit host addresses. Suppose a router has four links, numbered 0 through 3, and packets are to be forwarded to the link interface as shown in Table 1.
![alt text](https://github.com/Kayui/tsamnotes/blob/master/Main%20Exam%202015/table1.png "Table 1")
* Provide a forwarding table that has five entries, uses longest prefix matching and CIDR addresses, and forwards packets to the correct link interface.
    * 224.000.000.000/10&nbsp;&nbsp;&nbsp;0
    * 224.064.000.000/16&nbsp;&nbsp;&nbsp;1
    * 224.000.000.000/8&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2
    * 225.000.000.000/9&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2
    * Otherwise&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3
* Describe how your forwarding table determines the appropriate link interface for datagrams with the destination addresses:
    * 200.145.81.85
        * ANSWER
    * 224.64.195.60
        * ANSWER
    * 225.128.17.119
        * ANSWER
