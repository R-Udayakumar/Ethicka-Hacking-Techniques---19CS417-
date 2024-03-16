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
![image](https://github.com/R-Udayakumar/Ethicka-Hacking-Techniques---19CS417-/assets/118708024/f7c4e407-1205-4dc6-9007-84106408f117)

### Client :
![image](https://github.com/R-Udayakumar/Ethicka-Hacking-Techniques---19CS417-/assets/118708024/30c926f7-ba75-4573-a719-f0caf3f8b1a3)


## RESULT:
The program is executed successfully
