---
title: "Web Basics - Part 2"
datePublished: Sun Mar 12 2023 21:12:26 GMT+0000 (Coordinated Universal Time)
cuid: clf5w64yk000209ledcmxd8he
slug: web-basics-part-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678653909464/2f9c2799-5bef-472a-aa0c-fa0670ba9e2c.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1678655537126/587f3502-2f6d-4f54-9072-a16bbfdadf32.png
tags: http, smtp, tcp, protocols, ip-address

---

### Introduction to Protocols

Protocols are essential to modern communication, enabling devices to exchange information over networks in a standardized and reliable manner. Put simply, a protocol is a set of rules that governs how data is transmitted and received between different devices on a network. These rules ensure that data is transmitted correctly and that devices are able to understand and interpret the data they receive.

The need for protocols arose as computer networks became more widespread, with different types of devices and software needing to communicate with each other over a common network. After the invention of the ARPANet, multiple networks were created, leading to compatibility issues and communication problems between different devices. This problem was addressed by the development of standardized protocols that could be used across different networks and devices.

Today, there are numerous networking protocols in use, ranging from the well-known HTTP protocol used for transmitting data over the web, to the complex TCP/IP protocol suite that forms the backbone of the internet. Understanding these protocols is essential for anyone who works with computers or computer networks, as it allows them to troubleshoot problems, optimize network performance, and ensure that their systems are secure and reliable.

### Types of Internet Protocols

There are multiple Internet Protocols. Each of them is described in detail here:

1. **TCP/IP** is a protocol suite that provides the fundamental communication protocols for the internet and most modern computer networks. It was developed in the 1970s by the United States Department of Defense, and it is now widely used in both public and private networks. These are a set of standard rules that allows different types of computers to communicate with each other. The IP protocol ensures that each computer that is connected to the Internet is having a specific serial number called the **IP address**. TCP specifies how data is exchanged over the internet and how it should be broken into IP packets. It also makes sure that the packets have information about the source of the message data, the destination of the message data, the sequence in which the message data should be re-assembled, and checks if the message has been sent correctly to the specific destination. The TCP is also known as a connection-oriented protocol. TCP/IP is composed of four layers, each of which performs a specific set of functions:
    
    1. **Application layer**: The application layer is the top layer of the TCP/IP protocol stack. It is responsible for handling the specific protocols used by applications, such as HTTP for web browsing, SMTP for email, and FTP for file transfers.
        
    2. **Transport layer**: The transport layer is responsible for ensuring that data is transmitted reliably and accurately between devices. This layer uses two protocols: TCP (Transmission Control Protocol) and UDP (User Datagram Protocol). TCP is a connection-oriented protocol that provides reliable transmission of data, while UDP is connectionless and is used for applications that require the fast and lightweight transmission of data.
        
    3. **Internet layer**: The internet layer is responsible for addressing and routing data across networks. This layer uses the Internet Protocol (IP) to assign unique addresses to devices and to determine the best path for data to travel from the source to the destination.
        
    4. Link layer: The link layer is the lowest layer of the TCP/IP protocol stack. It is responsible for transmitting data over physical media, such as Ethernet or Wi-Fi. This layer is responsible for data framing, error detection, and flow control.
        
    
    Together, these four layers of the TCP/IP protocol suite provide a standardized set of protocols that allow devices to communicate with each other over networks, regardless of their underlying hardware or software.
    
    ![Network Protocols and the 4 Layer Model - YouTube](https://i.ytimg.com/vi/MVihcigDlbA/maxresdefault.jpg align="left")
    
2. **HTTP** (Hypertext Transfer Protocol) is a protocol used for transmitting data over the World Wide Web. It is a part of the application layer of the TCP/IP protocol suite. HTTP is used by web browsers, such as Google Chrome and Mozilla Firefox, to access web pages on the internet. HTTP works by establishing a connection between the user's computer and the web server hosting the web page, after which the server sends the web page data to the user's computer. HTTP supports a variety of data types, including text, images, and video. This protocol defines how the information needs to be formatted and transmitted. And, it also defines the various actions the web browsers should take in response to the calls made to access a  particular web page.
    
3. **FTP** (File Transfer Protocol) is a protocol used for transferring files between two devices over a network. It is a part of the application layer of the TCP/IP protocol suite. FTP is used by users to upload and download files from a remote server. FTP works by establishing a connection between the user's computer and the remote server, after which the user can transfer files to and from the server. When a machine requests for file transfer from another machine, the FTO sets up a connection between the two and authenticates each other using their ID and Password. And, the desired file transfer takes place between the machines.
    
4. **SMTP** (Simple Mail Transfer Protocol) is a protocol used for sending and receiving email messages over the internet. It is a part of the application layer of the TCP/IP protocol suite. SMTP is used by email clients, such as Microsoft Outlook, to send emails to an SMTP server, which then forwards the email to its intended recipient. SMTP works by establishing a connection between the email client and the SMTP server, after which the client sends the email message to the server, which then relays the message to the recipient's email server. This protocol uses the header of the mail to get the email id of the receiver and enters the mail into the queue of outgoing mail. And as soon as, it delivers the mail to the receiving email id, it removes the email from the outgoing list. The message or the electronic mail may consider the text, video, image, etc. It helps in setting up some communication server rules.
    
5. **SFTP(Secure File Transfer Protocol):** SFTP which is also known as SSH FTP refers to File Transfer Protocol (FTP) over Secure Shell (SSH) as it encrypts both commands and data while in transmission. SFTP acts as an extension to SSH and encrypts files and data then sends them over a secure shell data stream. This protocol is used to remotely connect to other systems while executing commands from the command line.
    
6. **HTTPS(HyperText Transfer Protocol Secure):** HTTPS is an extension of the Hypertext Transfer Protocol (HTTP). It is used for secure communication over a computer network with the SSL/TLS protocol for encryption and authentication. So, generally, a  website has an HTTP protocol but if the website is such that it receives some sensitive information such as credit card details, debit card details, OTP, etc then it requires an SSL certificate installed to make the website more secure. So, before entering any sensitive information on a website, we should check if the link is HTTPS or not. If it is not HTTPS then it may not be secure enough to enter sensitive information.
    
7. **SFTP(Secure File Transfer Protocol):** SFTP which is also known as SSH FTP refers to File Transfer Protocol (FTP) over Secure Shell (SSH) as it encrypts both commands and data while in transmission. SFTP acts as an extension to SSH and encrypts files and data then sends them over a secure shell data stream. This protocol is used to remotely connect to other systems while executing commands from the command line.
    
8. **ICMP** (Internet Control Message Protocol) is a network protocol that is used to send error messages and operational information about network conditions. It is an integral part of the Internet Protocol (IP) suite and is used to help diagnose and troubleshoot issues with network connectivity. ICMP messages are typically generated by network devices, such as routers, in response to errors or exceptional conditions encountered in forwarding a datagram. Some examples of ICMP messages include:
    
    * Echo Request and Echo Reply (ping)
        
    * Destination Unreachable
        
    * Time Exceeded
        
    * Redirect
        
    
    ICMP can also be used by network management tools to test the reachability of a host and measure the round-trip time for packets to travel from the source to the destination and back. It should be noted that ICMP is not a secure protocol, it can be used in some types of network attacks like DDoS amplification.
    
9. **UDP** (User Datagram Protocol) is a connectionless, unreliable transport layer protocol. Unlike TCP, it does not establish a reliable connection between devices before transmitting data, and it does not guarantee that data packets will be received in the order they were sent or that they will be received at all. Instead, UDP simply sends packets of data to a destination without any error checking or flow control. UDP is typically used for real-time applications such as streaming video and audio, online gaming, and VoIP (Voice over Internet Protocol) where a small amount of lost data is acceptable and low latency is important. UDP is faster than TCP because it has less overhead. It doesn’t need to establish a connection, so it can send data packets immediately. It also doesn’t need to wait for confirmation that the data was received before sending more, so it can transmit data at a higher rate.
    
10. **IMAP** (Internet Message Access Protocol) is a protocol used for retrieving emails from a mail server. It allows users to access and manage their emails on the server, rather than downloading them to a local device. This means that the user can access their emails from multiple devices and the emails will be synced across all devices. IMAP is more flexible than POP3 (Post Office Protocol version 3) as it allows users to access and organize their emails on the server, and also allows multiple users to access the same mailbox.
    

---

**NOTE:** An SSL (Secure Sockets Layer) certificate is a digital certificate that encrypts and authenticates data transmission over the internet. It is used to establish a secure connection between a web server and a web browser or other client software, ensuring that all data transferred between the two is encrypted and cannot be intercepted or tampered with by unauthorized third parties.

SSL certificates are issued by trusted third-party Certificate Authorities (CAs) after verifying the identity of the website owner and ensuring that they have the legal right to use the domain name associated with the website. Once installed on the web server, the SSL certificate activates the HTTPS protocol, which adds an additional layer of security to the standard HTTP protocol used for web communication.

When a user accesses a website with an SSL certificate, their web browser checks the certificate to ensure that it is valid and issued by a trusted CA. If the certificate is valid, the browser initiates a secure session with the website, which encrypts all data transmitted between the two parties using a cryptographic key.

SSL certificates are essential for protecting sensitive information, such as personal data, login credentials, and financial transactions, from interception or theft by hackers or other malicious actors. They are widely used by e-commerce sites, banks, healthcare providers, and other organizations that handle sensitive information online.

---

### Are all these protocols children of TCP/IP?

Not all of the protocols I mentioned are directly related to TCP/IP, but many of them are used in conjunction with TCP/IP. For example, DNS, DHCP, SNMP, and SSH all operate at the network layer or transport layer of the TCP/IP protocol stack. SMTP, POP3, and IMAP operate at the application layer, which is the top layer of the TCP/IP protocol stack. RTP and RTSP are often used in conjunction with TCP/IP for streaming media over the internet. SIP is also an application layer protocol that is used for voice and video communication over IP networks. So while these protocols may not all be direct descendants of TCP/IP, they are often used together with TCP/IP to enable communication over computer networks and the internet.

![](https://miro.medium.com/v2/resize:fit:875/1*pb-b83P8BATBvQSTUiyGkQ.png align="left")

**NOTE**: **Not all the Protocols are mentioned. Only the important ones are listed above.** **Basic Knowledge about these protocols is enough to get started with Web Dev.**

### Some other important protocols.

1. **IPv4 and IPv6**: IPv4 (Internet Protocol version 4) and IPv6 (Internet Protocol version 6) are two different versions of the Internet Protocol, which is the fundamental protocol that is used for communication over the internet. IPv4 is the older of the two protocols and has been in use since the early days of the internet. It uses 32-bit addresses and is capable of supporting up to about 4.3 billion unique addresses. However, with the explosion of internet-connected devices in recent years, the available pool of IPv4 addresses has been rapidly depleted, leading to the adoption of IPv6. IPv6 uses 128-bit addresses, which allows for an almost unlimited number of unique addresses (about 340 undecillion, which is a number with 38 zeros). This is enough to provide every device on the planet with a unique address and allow for the continued growth of the internet. IPv6 also includes several other improvements over IPv4, including better support for quality of service (QoS) and security, as well as simpler address allocation and configuration. While IPv6 has been available for many years, the adoption of the new protocol has been slow due to the need to upgrade existing network infrastructure and devices to support the new standard. However, as the pool of available IPv4 addresses continues to shrink, the need for widespread adoption of IPv6 is becoming more urgent.
    
2. **SSH:** SSH (Secure Shell) is a protocol used for secure remote login and other secure network services. It provides a secure and encrypted way to remotely access and manage servers, network devices, and other computer systems. SSH uses public-key cryptography to authenticate the user and encrypt the data being transmitted, making it much more secure than traditional remote login protocols such as Telnet. SSH also allows for secure file transfers using the SCP (Secure Copy) and SFTP (Secure File Transfer Protocol) protocols. It is widely used in Unix-based operating systems and is also available for Windows. It is commonly used by system administrators, developers, and other technical users to remotely access and manage servers and other network devices.
    

---

We will talk more about IPs, Domains, Subnet Masks, and other related concepts in the next blog. This was just a packed blog containing all the basic theory stuff as a refresher. If you did find this helpful, stay tuned/like/all that good stuff. Will write on more topics. If you still have any questions/queries you can reach out to me on my [**LinkedIn**](https://www.linkedin.com/in/sbk2k1/) / [**GitHub**](https://github.com/sbk2k1) / [**Twitter**](https://twitter.com/sbk_2k1).

Cheers!