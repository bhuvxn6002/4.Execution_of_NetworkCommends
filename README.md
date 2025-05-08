# 4.Execution-Of-Network-Commends - Ping

## AIM :Use of Network commands in Real Time environment

## Software : Command Prompt And Network Protocol Analyzer

## Procedure: To do this EXPERIMENT- follows these steps:

In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer
All commands related to Network configuration which includes how to switch to privilege mode
and normal mode and how to configure router interface and how to save this configuration to
flash memory or permanent memory.
This commands includes

• Configuring the Router commands

• General Commands to configure network

• Privileged Mode commands of a router

• Router Processes & Statistics

• IP Commands

• Other IP Commands e.g. show ip route etc.

## PROGRAM:
### CLIENT:

```
# NAME : Rakshitha J
# REG NO: 212223240135

import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
while True:
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```

### SERVER:
```
#NAME : Bhuvaneshwaran H
#REG NO :212223240018 

import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```

## OUTPUT:

![Screenshot 2025-04-17 142303](https://github.com/user-attachments/assets/daeb193f-c046-477e-99ba-288964cf7cfa)

## RESULT:
Thus, the python program for simulating ping command was successfully executed.
