# EXP 1:Echoserver

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
### Server
```
import socket

HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)
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

### Client
```
import socket

HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"K ESWANTH KUMAR, 212223040046")
    data = s.recv(1024)

print(f"Received {data!r}")
```

## OUTPUT:
### Echo-server
<p style="width=500px ;">
![Screenshot (165)](https://github.com/user-attachments/assets/69347ca1-5bde-4267-a3ae-e3e279c5107c)
<\p>
### Echo-client
![Screenshot (164)](https://github.com/user-attachments/assets/4359c660-3d3e-4dad-8210-a7f6ab23f635)

## RESULT:
The program is executed successfully
