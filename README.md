# Chatroom
Implements a local chatroom simulator accessible via the command line with a client program and a server program in which users may log in, message others, log out, etc. 
Download chatroom.zip and extract server.py and client.py from it into the directory of your choosing. Open up a terminal for the server program and run it with `python server.py`, then open up at least two terminals and run client.py in each of them. The server process will display in the terminal whatever the users are doing / chatting. There is currently a limit of three on the number of users that may join a server to chat. This must be changed in the source code itself via the variable MAXCLIENTS in server.py. 

Available commands include: 
1. login UserID Password       
The client first checks the correct usage of the command, and, if correct, sends the command to the 
server. If the server can verify the UserID and the Password, the server will send a confirmation 
message to the client and inform all other clients that this client joins the chat room; otherwise, the 
server will decline login and send an error message to the client.

2. newuser UserID Password                 
Creates a new user account. A new user can invoke the newuser command to create an account (we 
don't assume an administrator in this scenario). The length of the UserID should be between 3 and 32 
characters, and the length of the Password should be between 4 and 8 characters. UserID and 
Password are case-sensitive.
The client first checks the correct usage of the command (including correct lengths of UserID and 
Password), and, if correct, sends the command to the server. The server will reject the request if the 
UserID is already there. The users’ IDs and passwords are kept in the given file users.txt on the 
server side.

3. send all message  
Send the “message” to the server. The server will precede the message with the UserID of the sender 
and broadcast the message to all other clients. Message size can be between 1 and 256 characters.

4. send UserID message 
Send the “message” to the server. The server will precede the message with the UserID of the sender 
and unicast the message to the client “UserID”. Message size can be between 1 and 256 characters.

5. who  
List all the users in the chat room (including the user who issued the who command).

6. logout                           
Logout from the chat room. The connection between the server and client will be closed and the 
client will exit. The server will continue running and allow other clients to connect.  
