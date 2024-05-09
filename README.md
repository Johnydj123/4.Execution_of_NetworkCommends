# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## PROGRAM:
## CLIENT:
```
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

## SERVER
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```

## TRACER:

```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```


## Output
## CLIENT:
![WhatsApp Image 2024-05-10 at 00 39 30_6c60f496](https://github.com/Johnydj123/4.Execution_of_NetworkCommends/assets/145953459/dabf0b56-a340-4f4b-9cc2-727e6494c339)

## SERVER:
![WhatsApp Image 2024-05-10 at 00 39 44_8788c387](https://github.com/Johnydj123/4.Execution_of_NetworkCommends/assets/145953459/70ee469f-e66b-4ca6-9205-1cf4ab63fb51)

## TRACER:
![WhatsApp Image 2024-05-10 at 00 39 05_3c163090](https://github.com/Johnydj123/4.Execution_of_NetworkCommends/assets/145953459/fe86accc-68d1-4edf-8b4e-0a53904bbf09)


## Result
Thus Execution of Network commands Performed 
