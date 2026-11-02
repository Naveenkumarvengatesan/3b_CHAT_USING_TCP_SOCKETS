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

Client:
~~~
import socket

with socket.socket() as s:
    s.connect(('localhost', 8000))
    while (msg := input("Client > ")) != "exit":
        s.sendall(msg.encode())
        print("Server >", s.recv(1024).decode())
~~~

Server:
~~~
import socket

with socket.socket() as s:
    s.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)
    s.bind(('localhost', 8000))
    s.listen(5)
    c, addr = s.accept()
    with c:
        while data := c.recv(1024):
            print("Client >", data.decode())
            c.sendall(input("Server > ").encode())
~~~
## OUPUT

<img width="1600" height="196" alt="image" src="https://github.com/user-attachments/assets/8829e6e0-e254-4b22-89d6-5dd6117a9613" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
