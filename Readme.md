# PCC

This repository houses the Performance Congestion Control project.

To setup PCC, run the following:

- Install dependencies:
```bash
sudo apt-get update && sudo apt-get install cmake python3.6-dev zlib1g-dev python3-pip 
```

- Build
```bash
cd src && make
```

This will produce two apps (pccclient and pccserver) in the src/app directory.

To test that PCC is functioning, you can run:


- Export path
```bash
export LD\_LIBRARY\_PATH=$LD\_LIBRARY\_PATH:`pwd`/core/
```

- Start listener 
```bash
./app/pccserver recv 9000
```
(this creates a PCC server that listens on port 9000 and receives data)

and in a separate terminal, run:


```bash
export LD\_LIBRARY\_PATH=$LD\_LIBRARY\_PATH:`pwd`/core/
```

```bash
./app/pccclient send 127.0.0.1 9000
```
(this create a PCC client that connects to the local host (IP 127.0.0.1) at port 9000, then sends data to the server at that address.


## Known issues
Running the server and listener on localhost doesn't work. [ Mahimahi ](http://mahimahi.mit.edu/) (creates virtual network) can be an alternative, or start the listener and sender on two separate machines.
