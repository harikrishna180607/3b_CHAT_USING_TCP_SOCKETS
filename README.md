# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
## Server Side
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)

print("Waiting for client...")

c, addr = s.accept()

print("Connected with", addr)

while True:
    ClientMessage = c.recv(1024).decode()

    if ClientMessage == "bye":
        break

    print("Enter the Message from Client >", ClientMessage)

    msg = input("Receive the message for Client > ")

    c.send(msg.encode())

c.close()
s.close()
```
## Client Side
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Enter the Message On Client Site: ")

    if msg == "bye":
        break

    s.send(msg.encode())

    reply = s.recv(1024).decode()
    print("Enter the message from Server >", reply)

s.close()

```
## OUPUT
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/f7da7a75-8f3a-4328-9e93-1add4640cfea" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/b12dd71f-b0a5-4370-9942-b281f217cc9c" />


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
