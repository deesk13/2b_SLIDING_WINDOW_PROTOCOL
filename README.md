# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
# NAME: DEVA DHARSHINI I

# REGISTER NO: 212223240026

## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
CLIENT
```import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
```
SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
CLIENT
![Screenshot 2024-05-06 161519](https://github.com/deesk13/2b_SLIDING_WINDOW_PROTOCOL/assets/150927063/a6df7764-4adb-4356-a1e6-9c7e1f8cf7fa)
SERVER
![Screenshot 2024-05-06 161536](https://github.com/deesk13/2b_SLIDING_WINDOW_PROTOCOL/assets/150927063/6e94fd72-9cbd-474e-82d2-d47ff93ad07c)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
