# TCP/IP-Handshake (SYN | SYN-ACK | ACK)
**This demonstration is just to show you how the three-way handshake works and a little explanation on each flags.**

The TCP/IP three-way handshake is a fundamental aspect of network communication, serving as the cornerstone for establishing reliable connections between devices on the Internet. Understanding how this handshake works is crucial for network engineers, security analysts, and anyone involved in network infrastructure management. In the event of a security incident, such as a data breach or network intrusion, knowledge of the TCP handshake enables security personnel to conduct forensic analysis. They can examine captured network traffic to reconstruct the sequence of events leading up to the incident, identify the point of compromise, and determine the extent of unauthorized access.

In this project, I demonstrated how the TCP/IP three-way handshake works. I set up a pretend client and server, then watched how they talk to each other using a tool called tcpdump to capture the traffic. I opened three different command line interfaces, The first will start listening for incoming connections, and the second one will be used to capture network traffic, and the third terminal attempt to establish a TCP connection to the specified IP address which is my local machine.



First, the client sent a "SYN" message to the server, asking to start a connection. The server responded with a "SYN-ACK" message, acknowledging the request and also sending its own request to start a connection. Finally, the client sent an "ACK" message back to the server, confirming the connection was established. This helped me understand how they start and finish a connection.

