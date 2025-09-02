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

Clien Code
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
Server Code
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
````
## OUTPUT

<img width="1050" height="285" alt="image" src="https://github.com/user-attachments/assets/374ed0ff-43bc-47bd-aaf2-765befe94ea2" /><img width="1047" height="277" alt="image" src="https://github.com/user-attachments/assets/df435bbb-4138-4605-a55b-8230d91bcb59" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
