# 2a_Stop_and_Wait_Protocol

### NAME: NARESH.R
### ROLL NO :212223240104

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
### Client
```python
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
### Server
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## clint
![Screenshot 2024-05-17 133516](https://github.com/feryjfgkuyfgewjfgew/2a_Stop_and_Wait_Protocol/assets/150319377/6e15bd9d-b44a-454f-8073-43cba6d804ff)

## server
![Screenshot 2024-05-17 133457](https://github.com/feryjfgkuyfgewjfgew/2a_Stop_and_Wait_Protocol/assets/150319377/092343ca-5ce3-43fd-a7f9-1a0ffa9b1426)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
