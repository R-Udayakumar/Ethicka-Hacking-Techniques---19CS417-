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
### Server.py
```python
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
            data = conn.recv(1024).decode()
            if not data:
                break
            conn.sendall(data.encode())
```
### Client.py
```python
   
import socket
HOST = "127.0.0.1" 
PORT = 65432 
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
       s.sendall(input().encode()) 
       data = s.recv(1024).decode()
       print(f"Received {data!r}")
```         
## OUTPUT:
### Server :
![server](https://github.com/skiruthika648/Ethicka-Hacking-Techniques---19CS417-/assets/128348968/dc9f0986-f6d2-4bdd-b62d-976cf1e6d31f)

### Client :
![client](https://github.com/skiruthika648/Ethicka-Hacking-Techniques---19CS417-/assets/128348968/90d20375-9f3b-44bd-a4b5-2a7a0802c2f6)


## RESULT:
The program is executed successfully
