# Part 8: Network Server Code
#### Consider the source code of a network server below:
```c
#include <sys/socket.h>
#include <netinet/in.h>
#include <string.h>

int main(int argc, char **argv)
{
    int sockfd;
    struct sockaddr_in server, client;
    char message[512];

    sockfd = socket(AF_INET, SOCK_DGRAM, 0);
    memset(&server, 0, sizeof(server));
    server.sin_family = AF_INET;
    server.sin_addr.s_addr = htonl(INADDR_ANY);
    server.sin_port = htons(51966);
    bind(sockfd, (struct sockaddr *) &server, (socklen_t) sizeof(server));

    for(;;) {
        socklen_t len = (socklen_t) sizeof(client);
        recvfrom(sockfd, message, sizeof(message) - 1, 0, (struct sockaddr *) &client, &len);
        printf("%s:%d said %s\n", inet_ntoa(client.sin_addr), ntohs(client.sin_port), message);
    }
}
```
* What transport protocol is used by this program?
    * socket(AF_INET, SOCK_DGRAM, 0) is using SOCK_DGRAM = UDP
* What network protocol is used by this program?
    * socket(AF_INET, SOCK_DGRAM, 0) is using AF_INET = IPv4 (AF_INET6 = IPv6)
* What does this program do?
    * It waits for a message from a client and prints it to stdout.
*  Identify and explain the main network functions used in this program.
    * sockfd = sockfd = socket(AF_INET, SOCK_DGRAM, 0); Creates a new IPv4 socket that uses UDP for transport.
    * bind(sockfd, (struct sockaddr *) &server, (socklen_t) sizeof(server)); Assigns a address or "name" to the socket.
    * recvfrom(sockfd, message, sizeof(message) - 1, 0, (struct sockaddr *) &client, &len); waits for a message from a client.
* This program contains a security error
    * In what line is the error?
        * ANSWER
    * What security property may be violated by this error?
        * ANSWER
    * How would you correct the error?
        * ANSWER
