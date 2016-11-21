# Part 9: Network Server Code
#### Consider the source code of a network server below:
```c
#include <sys/socket.h>
#include <netinet/in.h>
#include <string.h>
#include <unistd.h>

int main(int argc, char **argv)
{
    int sockfd;
    struct sockaddr_in server;

    sockfd = socket(AF_INET, SOCK_STREAM, 0);
    memset(&server, 0, sizeof(server));
    server.sin_family = AF_INET;
    server.sin_addr.s_addr = htonl(INADDR_ANY);
    server.sin_port = htons(32000);
    bind(sockfd, (struct sockaddr *) &server, (socklen_t) sizeof(server));

    listen(sockfd, 1);

    for (;;) {
        char message[4096];
        int fd = accept(sockfd, NULL, NULL);
        recv(fd, message, sizeof(message) - 1, 0);
        send(fd, message, sizeof(message), 0);
        shutdown(fd, SHUT_RDWR);
        close(fd);
    }
}
```
* What transport protocol is used by this program?
   * socket(AF_INET, SOCK_STREAM, 0); is using SOCK_STREAM which is TCP.
* What network protocol is used by this program?
    * socket(AF_INET, SOCK_STREAM, 0); is using AF_INET which is IPv4. IPv6 would be AF_INET6
* What does this program do?
    * It accepts a client connection, waits for a message and sends it back, and closes connection.
*  Identify and explain the main network functions used in this program.
    * sockfd = socket(AF_INET, SOCK_STREAM, 0); Creates a new IPv4 socket that uses tcp for transport.
    * bind(sockfd, (struct sockaddr *) &server, (socklen_t) sizeof(server)); Assigns a address or "name" to the socket.
    * listen(sockfd, 1); Waits for connections on socket fd. the socket is now listening on the port bound (32000).
* This program contains a security defect 
    * In what line is the failure?
        * send(fd, message, sizeof(message), 0). This should be strlen(message), otherwise it will send the whole message buffer.
    * What security property may be violated by this defect?
        * Sensitive Data Protection Vulnerability. it will leak data from other clients or whatever happens to be in the buffer at the time.
    * How would you correct the fault?
        * change it to send(fd, message, strlen(message), 0).
        * also setting a null terminator to the end of the message, after receiving it.
