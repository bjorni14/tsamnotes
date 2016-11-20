# Part 7: Network Security
#### In what way does a hash provide a better message integrity check than a checksum (such as the Internet checksum)?
* An Internet checksum does not attempt to prevent collisions.

#### Can you “decrypt” a hash of a message to get the original message? Explain your answer.
* No, a hash algorithm has no inverse by design. This allows secure storage of passwords. This allows for fairly secure storing of passwords, brute forcing can always be applied if the hashing algorithm is known.

#### Suppose Alice and Bob are communicating over an SSL session. Suppose an attacker, who does not have any of the shared keys, inserts a bogus TCP segment into a packet stream with correct TCP checksum and sequence numbers (and correct IP addresses and port numbers). Will SSL at the receiving side accept the bogus packet and pass the payload to the receiving application? Why or why not? 
* No, the bogus packet will fail the integrity check ( which uses a shared MAC key)