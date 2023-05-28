# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

DATE : 27.05.23

AIM :
To write a python program to perform stop and wait protocol


ALGORITHM :
1 Start the program.

2.Get the frame size from the user

3.To create the frame based on the user request.

4.To send frames to server from the client side.

5.If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.

6.Stop the program


PROGRAM :

Developed by VISMAYA.S
Register number 212221230125
# CLIENT PROGRAM :
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
   i=input("ENter a data:")
   c.send(i.encode())
   ack=c.recv(1024).decode()
   if ack:
   	print(ack)
   	continue
   else:
   	c.close()
   	break
    
# SERVER PROGRAM :
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())    






OUTPUT:

# client 
![client](https://github.com/sujathamohankumar/19CS406-EX-1/assets/93427210/e697dd34-f7c7-41f9-8b43-d14c238b0340)

# server
![server](https://github.com/sujathamohankumar/19CS406-EX-1/assets/93427210/8cf4f951-6cb8-4fbf-9209-581ffe8eb3e1)




RESULT:

Thus, python program to perform stop and wait protocol was successfully executed.

