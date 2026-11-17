# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
## server.py
```
import socket
server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server.bind(('127.0.0.1',12345))
server.listen(1)
print("Echo Server is running...")
print("Waiting for client connection...\n")
conn, addr = server.accept()
print("Connected to client:", addr)
while True:
    data = conn.recv(1024).decode()
    if not data:
        break
    print("Received from client:", data)
    conn.send(data.encode())  # Echo back
conn.close()
server.close()
```

## client.py
```
import socket
client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client.connect(('127.0.0.1',12345))
while True:
    msg = input("Enter message (or 'byee' to stop): ")
    if msg.lower() == "byee":
        break
    client.send(msg.encode())
    reply = client.recv(1024).decode()
    print("Echo from server:", reply)
client.close()
```

## OUPUT
<img width="1916" height="1025" alt="image" src="https://github.com/user-attachments/assets/a236c99e-413b-46d5-850c-8e3bd4d21edb" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
