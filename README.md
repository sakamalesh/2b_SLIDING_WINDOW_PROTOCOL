# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## Name: Kamalesh
## Reg no:212223040083
## Server:
'''

    import socket
    s=socket.socket()
    s.connect(('localhost',8000))
    while True: 
     print(s.recv(1024).decode())
     s.send("acknowledgement recived from the server".encode())
'''
## client:
'''

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
  '''

## OUPUT
## Server:
![Screenshot 2024-09-14 103852](https://github.com/user-attachments/assets/38b05dc3-ef1e-4db2-b98b-082a40babd7a)

## client:
![Screenshot 2024-09-14 103843](https://github.com/user-attachments/assets/6cd2bbce-607e-4945-81cd-d95c5b3e3067)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
