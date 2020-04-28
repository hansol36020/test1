# dockerfiles-centos-user-adderable
ubuntu based
install net-tools
install curl
install tree

# Building & Running

Copy the sources to your docker host and build the container, and to run.
```
	docker build --rm -t hansol36020/curltree .
	docker run -it --name ct1 hansol36020/curltree
```
Get the port that the container is listening on:

```
# docker ps
CONTAINER ID        IMAGE                  COMMAND             CREATED             STATUS              PORTS          NAMES
58faf7f3014a        hansol36020/curltree   "/bin/bash"         6 minutes ago       Up 6 minutes                       ct1
```
To test, ("hansol36020" is username. ifconfig)
```
#ifconfig

eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.17.0.2  netmask 255.255.0.0  broadcast 172.17.255.255
        ether 02:42:ac:11:00:02  txqueuelen 0  (Ethernet)
        RX packets 33  bytes 3334 (3.3 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 20  bytes 1284 (1.2 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```
To test, ("hansol36020" is username. curl)
```
#curl google.com
<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="http://www.google.com/">here</A>.
</BODY></HTML>

`````````
To test, ("hansol36020" is username.tree )
```
#tree
|-- local
|-- lock -> /run/lock
|-- log
|   |-- alternatives.log
|   |-- apt
|   |   |-- eipp.log.xz
|   |   |-- history.log
|   |   `-- term.log
|   |-- bootstrap.log
|   |-- btmp
|   |-- dpkg.log
|   |-- faillog
|   |-- lastlog
|   `-- wtmp
|-- mail
|-- opt
|-- run -> /run
|-- spool
|   `-- mail -> ../mail
`-- tmp
```
