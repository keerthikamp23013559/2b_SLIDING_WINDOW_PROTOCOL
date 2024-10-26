# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
To Write Python Program To Implement The Sliding Window Protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### client
```
import socket
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
### server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  print(s.recv(1024).decode())
  s.send("acknowledgement received from the server".encode())
```
## OUPUT
![Screenshot 2024-10-26 211820](https://github.com/user-attachments/assets/cfb88675-d018-4850-8b1d-ed3ea52e8c86)
![Screenshot 2024-10-26 211830](https://github.com/user-attachments/assets/d3c0c511-20ff-440d-a7e9-21044dd9577e)

## RESULT
Thus, python program to perform sliding window protocol was successfully executed
