# Part 2: HTTP
#### Consider an HTTP client that wants to retrieve a Web document at a given URL. The IP address of the HTTP server is initially unknown. What transport and application-layer protocols besides HTTP are needed in this scenario?
* UDP for DNS querying and TCP for connecting to the website and grabbing the document.

#### Consider a short, 10 m link, over which a sender can transmit at a rate of 150 bit/s in both directions. Suppose that packets containing data are 100 000 bit long, and packets containing only control (e.g. ACK or hand-shaking) are 200 bit long. Assume that N parallel connections each get 1∕N of the link bandwidth. Now consider the HTTP protocol, and suppose that each downloaded object is 100 kbit long, and that the initial downloaded object contains 10 referenced objects from the same sender.
* Would parallel downloads via parallel instances of non-persistent HTTP make sense in this case? Justify your answer.
    * Distance: 10 m ( too short to bother with propagation time, we're talking nanoseconds )
    * Transmit Rate (__TR__): 150 bit/s
    * Data Packets (__DP__): 100 000 bit long
    * Control(handshake) Packets (__CP__): 200 bit long
    * N parallel connections get 1/N of the link bandwidth
    * Initial Download is 10 (__N__) referenced objects from the same sender
    * This gives us the following formula for the initial object: ((__CP__`*`3) + __DP__) / __TR__
        * This adds up to ((200 `*` 3) + 100000) / 150 = ~671 seconds
    * And the following formula for the remaining 10 objects: ((__CP__`*`3) + __DP__) / (__TR__ / __N__)
        * This adds up to ((200 `*` 3) + 100000) / (150/10) = ~6707 seconds
    * This all adds up to 671+6707 = ~7378 seconds
    * Yes, it would make sense.
* Now consider persistent HTTP. Do you expect significant gains over the non-persistent case? Justify and explain your answer.
    * Considering the same premise as above the only change is doing the ACK handshake once.
    * This gives us the __same__ formula for the initial object: ((__CP__`*`3) + __DP__) / __TR__
        * This adds up to ((200 `*` 3) + 100000) / 150 = ~671 seconds
    * And an altered formula for the remaining 10 objects: ((__CP__ / __TR__) + (__N__`*`(__DP__ / __TR__)))
        * This adds up to ((200/150) + (10*(100000/150))) = 6668 seconds
    * This all adds up to ~671 + 6668 = ~7339
    * This gives us a difference of ~39 seconds which is relatively small considering the total time.