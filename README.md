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
![Screenshot 2025-03-17 103414](https://github.com/user-attachments/assets/f35836f9-0cf4-4b84-9852-b2f281d33633)
![Screenshot 2025-03-17 103430](https://github.com/user-attachments/assets/bbdbef3a-f3ce-45e6-8a89-b9cde2fb360e)
![Screenshot 2025-03-17 103445](https://github.com/user-attachments/assets/27ebc8a0-4993-48ca-ae05-cd3ae195aaeb)
![Screenshot 2025-03-17 103500](https://github.com/user-attachments/assets/1aaa77b3-3034-4630-935c-aeed74f3faf3)

## RESULT:
The program is executed successfully
