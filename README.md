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







