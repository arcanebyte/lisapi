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

The LisaNet admin can be reached at `arcanepi!ulisa!james` or
`james@arcanebyte.com`. If all else fails, Internet email at `james.denton@outlook.com
should work.

## Using this playbook

To configure UUCP in the intermediary, clone this playbook:

```
cd ~/
git clone https://github.com/arcanebyte/lisapi
```

Copy the example overrides file to `overrides.yml`:

```
cp ~/lisapi/overrides.yml.example ~/lisapi/overrides.yml
```

Edit `overrides.yml` and change the following values:

```
rpi_name
lisa_name
call_login
call_password
```

The `rpi_name` and `lisa_name` should be unique names less than 8
characters in length. Consult the LisaNet admin for suitable names
and to avoid conflict with other sites.

To run the playbook and configure UUCP, run the following on the
intermediary host:

```
cd ~/lisapi
sudo ansible-playbook -e @overrides.yml uucp.yml
```

## Connecting to LisaNet

To connect to LisaNet, it may be necessary to open your firewall to
UUCP traffic on TCP port 540. It may also be necessary to create a port
translation to allow connections to the local intermediary host over
the Internet through an edge router or firewall. The LisaNet community
may be able to assist with this configuration.
