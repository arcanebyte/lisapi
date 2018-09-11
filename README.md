# LisaPi

LisaPi is an image that can be installed on a Raspberry Pi and is
preconfigured to connect to an Apple Lisa using the UUCP suite of
tools.

The LisaNet UUCP network currently consists of a single Apple Lisa 2/5 and an
intermediary Raspberry Pi located in Dayton, Ohio in the United States.

```
LISANET LOGICAL MAP
------------------------------------------------------------------------------


                                      ulisa
                                        |
                                        |
                                     arcanepi


------------------------------------------------------------------------------
```

The UUCP network is a store and forward network. Electronic mail directed to
users may be stored along the path until the furthermost host is available to
receive the payload.

Mail can be directed to `host!user` if a direct path is available. In the
absence of a direct connection, intermediary hosts using TCP/IP can be used.
Individual hosts and users are separated on the **bang** path using
exclamation `!` marks, like `intermediary!host!user`.

The LisaNet admin can be reached at `arcanepi!ulisa!james` or `james@arcanebyte.com`.

