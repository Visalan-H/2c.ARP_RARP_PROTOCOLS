# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.

#### Developed By: Visalan H
#### Register Number: 212223240183

## Program - ARP

```
import socket
s=socket.socket()
s.bind(('localhost',8880))
s.listen(5)
c,addr=s.accept()
address={"192.168.144.56":" AC:50:DE:1B:DE:65"};
while True:
ip=c.recv(1024).decode()
try:
c.send(address[ip].encode())
except KeyError:
c.send("Not Found".encode())
```
## OUTPUT - ARP

![image](https://github.com/user-attachments/assets/4bd4e387-6dd7-48d0-8d99-d7fb2cb3e978)

## Program - RARP

```
import socket
s=socket.socket()
s.connect(('localhost',8880))
while True:
ip=input("Enter Logical Address:")
s.send(ip.encode())
print("MAC address",s.recv(1024).decode())
```

## OUTPUT -RARP

![image](https://github.com/user-attachments/assets/0120a617-b99b-4821-b559-f4ca7516ce55)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
