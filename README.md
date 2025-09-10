# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## name:joshithashree bs
## reg no:212224230107
## AIM
To write a python program to perform Sliding window protocol and verify .
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## server side:
## program
```
#server
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowlegement received from the server".encode())
```
## output

<img width="274" height="84" alt="Screenshot 2025-09-10 112528" src="https://github.com/user-attachments/assets/6f0abdb1-df75-4274-8422-18d8adccd013" />


## PROGRAM
## client side
```
#client
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send: "))
l=list(range(size))
s=int(input("Enter window size : "))
st=0
i=0
while True:
    while(i<len(l)):
        st=st+s
        c.send(str(l[i:st]).encode())
        ack=c.recv(1024).decode()
        if ack:
            print(ack)
            i=i+s
```
## OUPUT
<img width="574" height="123" alt="Screenshot 2025-09-10 112521" src="https://github.com/user-attachments/assets/c3aaedc9-6c29-4ccd-8c88-75a196b4103f" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
