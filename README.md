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
SERVER.PY:
~~~
import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    print("Server is listening...")

    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
~~~
CLIENT.PY:
~~~
import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    message = "Hello, world!"
    s.sendall(message.encode())
    data = s.recv(1024)
    print(f"Received {data.decode()}")
~~~


## OUTPUT:
![alt text](422811639-84533438-45a7-4c14-97cf-8b06aa1bd1d4-2.png)
![alt text](2-2.png)
![alt text](3-1.png)
![alt text](4-1.png)

## RESULT:
The program is executed successfully
