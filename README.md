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
# client:
```py
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
# server:
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())

```
## OUTPUT
# client:
![Screenshot 2024-03-01 111236](https://github.com/codedbykishore/2a_Stop_and_Wait_Protocol/assets/147139122/2d9657d4-10cb-471c-8d54-23b3aab326a8)

# server:
![Screenshot 2024-03-01 111308](https://github.com/codedbykishore/2a_Stop_and_Wait_Protocol/assets/147139122/5f843a7a-aff0-4185-86a0-b8e29af2e314)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
