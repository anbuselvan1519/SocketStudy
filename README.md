# Ex.No:1-a Study of Socket Programming

## Name: Anbuselvan.S
## Register No: 212223240008

## Aim: 
To perform a study on Socket Programming.

## Introduction:
Socket programming is a crucial aspect of network communication, allowing for data exchange between computers over a network. It forms the backbone of various networked applications, enabling communication between clients and servers. This study explores the fundamental concepts of socket programming, its use cases, and provides a practical example to demonstrate its implementation.
## Understanding Socket Programming:
Socket programming involves the use of sockets, which serve as endpoints for communication. A socket is identified by an IP address and a port number, and it facilitates data transfer between a client and a server. The two main types of sockets are Stream Sockets, which provide a reliable, connection-oriented communication, and Datagram Sockets, which are connectionless and suitable for scenarios where reliability is less critical.
## Key Concepts in Socket Programming:
 Socket Programming Basics

 1. Sockets
 A socket is a software representation of a communication endpoint in a network.
 It is identified by an IP address and a port number.
 Sockets can be classified into two main types:
  - Stream Sockets: Provide reliable, connection-oriented communication.
  - Datagram Sockets: Connectionless and operate in a best-effort mode.

 2. Client-Server Model
 Socket programming typically follows the client-server model.
  - The server listens for incoming connections from clients.
  - The client initiates connections to the server.
  - Servers are passive, waiting for connection requests.
  - Clients are active, initiating communication.

 3. TCP/IP Protocol
 TCP (Transmission Control Protocol) and IP (Internet Protocol) are the foundational protocols for socket programming.
  - TCP: Provides reliable, connection-oriented communication, ensuring data integrity and order.
  - IP: Facilitates the routing of data between devices in a network.

 4. Basic Socket Functions
 Socket programming involves a set of functions to create, bind, listen, accept, connect, send, and receive data through sockets.
 Examples of functions:
  - socket()
  - bind()
  - listen()
  - accept()
  - connect()
  - send()
  - recv()

 5. Server-Side Operations
 Servers create a socket using the socket() function.
 They bind the socket to a specific IP address and port using bind().
 The server then listens for incoming connections with listen().
 Connections are accepted using accept().
 Once a connection is established, the server can send and receive data using send() and recv().

## Client –Server Operations

Clients create a socket using socket() and connect to a server using connect().
After establishing a connection, clients can send and receive data using send() and recv().

## Use Cases of Socket Programming:
Socket programming finds applications in various domains, including web development, file transfer protocols, online gaming, and real-time communication. It is the foundation for protocols like HTTP, FTP, and SMTP, which power the internet. Socket programming enables the development of both server and client applications, facilitating the exchange of information between devices in a networked environment.
## Example Use Cases:

1.	Web servers: Web servers use socket programming to handle incoming HTTP requests from clients, serving web pages and content.
2.	Chat Application: Instant messaging and chat applications use sockets to enable real-time communication between users.
3.	File Transfer Protocol: Protocols like FTP (File Transfer Protocol) utilize socket programming for transferring files between a client and a server.
4.	Networked Games: Online multiplayer games rely on socket programming to facilitate communication between game clients and servers.
5.	RPC mechanisms: which allow processes to execute code on a remote server, often use socket programming for communication.

## Program:

### Server code:
```
import socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server_socket.bind(('127.0.0.1', 65432))
server_socket.listen()
print("Waiting for a client to connect...")
conn, addr = server_socket.accept()
print(f"Connected by {addr}")
data = conn.recv(1024)  # Hear what the client says
print(f"Client says: {data.decode()}") 
conn.sendall(b"Hello from Server!")  
conn.close()
```

### Client code:
```
import socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client_socket.connect(('127.0.0.1', 65432))
client_socket.sendall(b"Hello from Client!")  
data = client_socket.recv(1024)  
print(f"Server says: {data.decode()}")  
client_socket.close()
```

## Output:

### server:
![image](https://github.com/user-attachments/assets/8db7ab72-126d-46e6-baa6-602435b649d7)

### client:
![image](https://github.com/user-attachments/assets/f1e3772c-ea16-4c5b-a664-a4ec2b13222f)

## Result:
Thus the study of Socket Programming Completed Successfully
