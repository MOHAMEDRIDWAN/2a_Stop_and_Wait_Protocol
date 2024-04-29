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
## Program

# Client:
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

# Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```

## Output:
![Screenshot 2024-04-05 101810](https://github.com/Anas536/SocketStudy/assets/139841834/834ab42e-625b-4232-bca9-0392f767d629)


![Screenshot 2024-04-05 101821](https://github.com/Anas536/SocketStudy/assets/139841834/4781f25e-ca79-4fd8-801c-56dbbd580326)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
