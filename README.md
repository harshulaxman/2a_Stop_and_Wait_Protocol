# EX- 2a: Stop_and_Wait_Protocol

### Name: Harsshitha lakshmanan
### Register no: 212223230075
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
## Client
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
i=input("Enter a data: ")
c.send(i.encode())
ack=c.recv(1024).decode()
if ack:
print(ack)
continue
else:
c.close()
break
```
## Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
print(s.recv(1024).decode())
s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## Client side:
![image](https://github.com/user-attachments/assets/2b2e2e76-0eac-45cb-940c-d94523efa8d5)
## Server side:
![image](https://github.com/user-attachments/assets/045135fc-3b83-4d3e-8256-5dbde29eb82c)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
