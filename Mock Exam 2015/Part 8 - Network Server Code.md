# Part 8: Network Server Code
#### Consider the source code of a network server below
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