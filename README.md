# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
CLIENT SIDE:

import socket

HOST = "127.0.0.1"  # The server's hostname or IP address

PORT = 65432  # The port used by the server

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:

    s.connect((HOST, PORT))
    
    s.sendall(b"Hello, world")
    
    data = s.recv(1024)

print(f"Received {data!r}")

SERVER SIDE:

import socket

HOST = "127.0.0.1"  # Standard loopback interface address (localhost)

PORT = 65432  # Port to listen on (non-privileged ports are > 1023)

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:

    try:
    
        s.bind((HOST, PORT))
    
    except Exception as e:
    
        print(f"Error binding to {HOST}:{PORT}: {e}")
        
        exit()
    
    s.listen()
    
    print(f"Listening on {HOST}:{PORT}...")
    
    try:
    
        conn, addr = s.accept()
    
    except Exception as e:
    
        print(f"Error accepting connection: {e}")
        
        exit()
    
    with conn:
    
        print(f"Connected by {addr}")
        
        while True:
        
            try:
            
                data = conn.recv(1024)
                
                if not data:
                
                    break
                
                conn.sendall(data)
            
            except Exception as e:
            
                print(f"Error receiving/sending data: {e}")
                
                exit()
## OUTPUT:
SERVER SIDE:
![image](https://github.com/user-attachments/assets/8b868159-888c-41e4-af31-154a5b3bf61c)
CLIENT SIDE:
![image](https://github.com/user-attachments/assets/2874f95b-70fc-49e6-9c2a-cfab117634f8)


## RESULT:
The program is executed successfully
