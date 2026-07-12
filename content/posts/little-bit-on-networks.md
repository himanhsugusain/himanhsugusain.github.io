---
title: "Little bit on networks"
date: 2023-08-05T16:58:58Z
description: "Simple C code to do a DNS lookup."
tags:
  - cpp
  - networks
---

Simple c code to do a dns lookup.

<!--more-->

```cpp
#include <sys/types.h>
#include <sys/socket.h>
#include <netdb.h>
#include <stdio.h>
#include <netinet/in.h>
#include <arpa/inet.h>


int main()
{

  struct hostent *h = gethostbyname("www.google.com");

  printf("%s\n", inet_ntoa(*(struct in_addr *) h->h_addr));
}
```

This snippet was created to check wheather the underlying dns module was serving the same IP, overloading the server. Instead of `google.com` we obviously use an internal domain.
The point being proved here is that, `gethostbyname` randomize which IP it will return.
