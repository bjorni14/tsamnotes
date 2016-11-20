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
    * ANSWER
* What network protocol is used by this program?
    * ANSWER
* What does this program do?
    * ANSWER
*  Identify and explain the main network functions used in this program.
    * ANSWER
* This program contains a security defect 
    * In what line is the failure?
        * ANSWER
    * What security property may be violated by this defect?
        * ANSWER
    * How would you correct the fault?
        * ANSWER