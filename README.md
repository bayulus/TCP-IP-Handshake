# TCP/IP-Handshake (SYN | SYN-ACK | ACK) Demonstration

<img src="https://github.com/bayulus/TCP-IP-Handshake/blob/main/header.png?raw=true" >

**This demonstration is just to show you how the three-way handshake works and a little explanation on each flags.**

The TCP/IP three-way handshake is a fundamental aspect of network communication, serving as the cornerstone for establishing reliable connections between devices on the Internet. Understanding how this handshake works is crucial for network engineers, security analysts, and anyone involved in network infrastructure management. In the event of a security incident, such as a data breach or network intrusion, knowledge of the TCP handshake enables security personnel to conduct forensic analysis. They can examine captured network traffic to reconstruct the sequence of events leading up to the incident, identify the point of compromise, and determine the extent of unauthorized access.

In this project, I demonstrated how the TCP/IP three-way handshake works. I set up a pretend client and server, then watched how they talk to each other using a tool called **tcpdump to capture the traffic**. First, the client sent a "SYN" message to the server, asking to start a connection. The server responded with a "SYN-ACK" message, acknowledging the request and also sending its own request to start a connection. Finally, the client sent an "ACK" message back to the server, confirming the connection was established. This helped me understand how they start and finish a connection.

<h3>1. Setting up Connection and Capturing Traffic.</h3>
<p>I opened three different command line interfaces, The first terminal will start listening for incoming connections, the second terminal one will be used to capture network traffic, and the third terminal attempt to establish a TCP connection to the specified IP address which is my local machine.</p>

<img src="https://github.com/bayulus/TCP-IP-Handshake/blob/main/1.PNG?raw=true" >

<h3>2. Listening for Incoming Connection on Port 2222  </h3>
<p> After I execute this command nc -l -p 2222, Netcat springs into action, ready to accept incoming TCP connections on port 2222 of my local machine. Any data received on this port will be displayed on the standard output. The next step </p> 

<img src="https://github.com/bayulus/TCP-IP-Handshake/blob/main/2.PNG?raw=true" >

<h3>3. Capturing The Traffic </h3>
<p>After setting up the network listener with nc -l -p 2222, any incoming TCP connections and data sent to port 2222 on the local machine will be captured by the loopback interface (lo). By running tcpdump -i lo alongside nc -l -p 2222, I can observe and analyze the traffic being sent to and received from the network listener in real-time.

This setup allows me to inspect the communication between different processes or applications running on my local machine, providing insights into how they interact and exchange data. I can use it to monitor the behavior of my network listener, debug any issues related to incoming connections, or analyze the data exchanged between the listener and connecting clients.</p>

<img src="https://github.com/bayulus/TCP-IP-Handshake/blob/main/3.PNG?raw=true" >

<h3>4. Connecting to the Listening Port(Server)</h3>

<p>Now that I've set up a listener on port 2222 (acting as the server) using the command nc -l -p 2222, I want to establish a connection to this listener from my client. To do this, I used the command nc 127.0.0.1 2222 to communicate with the server that's listening on port 2222. In this setup, I play the role of the client, initiating the connection to the server's listening port.</p>

<img src="https://github.com/bayulus/TCP-IP-Handshake/blob/main/4.PNG?raw=true" >

<h3>4. The Captured Traffic</h3>

<img src="https://github.com/bayulus/TCP-IP-Handshake/blob/main/5.PNG?raw=true" >
<p>Now, traffic is captured showing the TCP handshake and how the connection is established.</p>

**Syn**

As shown in the image above, The first packet in red is trying to connect to port 2222. It sends a SYN (Synchronize) flag, indicating the initiation of a connection, and includes a sequence number **873455983**

**Syn-Ack (Increases Sequence Number by 1)** 

In response to the SYN request, the second packet sends back a SYN-ACK (Synchronize-Acknowledgment) flag. This signals that the server acknowledges the client's request and is willing to establish a connection. The packet includes an incremented sequence number **873455984** and acknowledges the received sequence number, confirming the synchronization.  The ACK number in the SYN-ACK packet indicates to the client that the server has received the initial SYN packet successfully. By incrementing the ACK number by 1 from the sequence number in the client's SYN packet, the server establishes the initial sequence number for the data it sends back to the client. This ensures that both sides agree on the initial sequence number for the data exchange.

**Ack**

The client acknowledges the receipt of the SYN-ACK packet from the server.
This acknowledgment confirms that the client has successfully received the SYN-ACK packet and acknowledges the server's acknowledgment of the SYN packet sent by the client. The ACK packet does not contain any data payload or flags other than the acknowledgment itself.
By sending the ACK packet, the client signals to the server that it is ready to proceed with the established connection, and both parties can now exchange data over the connection.

# Rounding Up

This sequence of SYN, SYN-ACK, and ACK packets constitutes the TCP three-way handshake, which is a fundamental process for establishing reliable connections in the TCP/IP protocol suite. It ensures that both parties agree on the initial sequence numbers and synchronize their communication, laying the groundwork for efficient and error-checked data transfer.









