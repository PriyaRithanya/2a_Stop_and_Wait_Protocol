# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
client side

import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())

server side

import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Waiting for connection...")
c, addr = s.accept()
print("Connected with", addr)
while True:
    i = input("Enter a data: ")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
    else:
        c.close()
        break
```
## OUTPUT
<img width="859" height="766" alt="Screenshot (154)" src="https://github.com/user-attachments/assets/ba7f9d35-c7f2-4582-ba81-0974abe1d578" />
<img width="1261" height="892" alt="Screenshot (155)" src="https://github.com/user-attachments/assets/5ba8882b-391d-495c-bc50-0d69a8c20277" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
