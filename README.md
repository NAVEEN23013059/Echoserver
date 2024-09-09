### Date: 09-09-2024
# Echoserver
Echo server and client using python socket


## AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
### Client.py
```
import socket
HOST = "127.0.0.1"
PORT = 65432
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT)) 
    s.sendall(b"Naveen S,")
    s.sendall(b"2122223240106")
    data = s.recv(1024)
print(f"\nRecived {data!r}")
```
### Server.py
```
import socket
HOST = "127.0.0.1" 
PORT = 65432
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
## OUTPUT:
![alt text](<output.png>)
## RESULT:
The program is executed successfully
