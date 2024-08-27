# 2a_Stop_and_Wait_Protocol

### NAME : MARIO VIOFER J
### REGISTER NO : 212223100032

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
### Client:
~~~
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
    else:
        c.close()
        break
~~~
### Server:
~~~
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
~~~
## OUTPUT
### Client:

![image](https://github.com/user-attachments/assets/790c5046-b465-4374-8622-549ef2b85f14)

### Server:

![image](https://github.com/user-attachments/assets/edae9852-cb01-4c6b-899a-d2697bb8c25d)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
