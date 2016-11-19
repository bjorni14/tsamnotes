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
    * ANSWER
* What network protocol is used by this program?
    * ANSWER
* What does this program do?
    * ANSWER
*  Identify and explain the main network functions used in this program.
    * ANSWER
* This program contains a security error
    * In what line is the error?
        * ANSWER
    * What security property may be violated by this error?
        * ANSWER
    * How would you correct the error?
        * ANSWER