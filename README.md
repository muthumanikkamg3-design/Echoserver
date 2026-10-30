# Echoserver

Name : MUTHU MANIKKAM G

REG.NO : 212225100029

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
 Server Code:

echo_server.py
~~~
import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()

    print("Server is waiting for a client...")

    conn, addr = s.accept()

    with conn:
        print("Connected by", addr)

        while True:
            data = conn.recv(1024)

            if not data:
                break

            conn.sendall(data)
~~~


Client Code:


echo_Client.py

~~~

import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))

    message = b"Hello, world"

    s.sendall(message)

    data = s.recv(1024)

print("Received:", data.decode())
~~~
## OUTPUT:

Server Output:

<img width="940" height="476" alt="image" src="https://github.com/user-attachments/assets/d36e010d-1a1b-4bff-a4eb-f1b981bef66e" />

Client Output:

<img width="940" height="476" alt="image" src="https://github.com/user-attachments/assets/3c3b8840-fd1c-4982-b6ba-70c29ea407da" />


## RESULT:
The program is executed successfully
