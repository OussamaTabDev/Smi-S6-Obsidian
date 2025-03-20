These are protocols organized by layers in the **TCP/IP model**, which is the foundation of modern networking. Let’s break them down by layer and function:

---

## **1. Application Layer (Couche application)**

This layer is where user applications interact with the network.

- **FTP (File Transfer Protocol)**  
    📂 Used for transferring files between computers over a network. It allows uploading and downloading of files but is not secure by default.
    
- **HTTP (Hypertext Transfer Protocol)**  
    🌐 The foundation of web browsing. It allows the transfer of web pages and other content. Modern web traffic often uses HTTPS, which is the secure version of HTTP.
    
- **SMTP (Simple Mail Transfer Protocol)**  
    📧 Used for sending emails. It works with other protocols like POP3 and IMAP for receiving emails.
    
- **DNS (Domain Name Service)**  
    🔤 Translates domain names (like `google.com`) into IP addresses (like `142.250.190.78`) so computers can find each other on the network.
    

---

## **2. Transport Layer (Couche transport)**

This layer ensures data is delivered correctly and efficiently.

- **TCP (Transmission Control Protocol)**  
    ✅ Reliable, connection-based protocol that ensures all data is received correctly and in order. Used for web browsing (HTTP), email (SMTP), and file transfers (FTP).
    
- **UDP (User Datagram Protocol)**  
    ⚡ Faster but unreliable, connectionless protocol. It’s used for real-time applications like video streaming, VoIP calls, and online gaming.
    

---

## **3. Internet Layer (Couche Internet)**

Handles addressing and routing of data across networks.

- **[[IP (Internet Protocol)]]**  
    🛣️ Defines IP addresses and ensures packets of data are routed correctly from sender to receiver.
    - **IPv4** (e.g., `192.168.1.1`) is the most widely used.
    - **IPv6** (e.g., `2001:db8::ff00:42:8329`) is newer and designed to replace IPv4 due to more available addresses.

---

## **4. Network Access Layer (Couche accès au réseau)**

Handles how data is physically transmitted over different types of networks.

- **Ethernet**  
    🔌 A wired networking technology used in most local networks (LANs). It connects devices using cables and switches.
    
- **Token Ring**  
    🔄 An older LAN technology that passes a "token" around the network to control access. Rarely used today.
    
- **Frame Relay**  
    📡 A WAN technology used for connecting remote offices before broadband and fiber became widespread.
    
- **Other LAN/WAN Technologies**  
    🌍 Includes Wi-Fi, fiber optics, satellite, DSL, and 5G networks.
    

---

### **Summary of How They Work Together**

1. A user types `google.com` in a browser (Application Layer - HTTP).
2. The computer asks a DNS server to get the IP address (Application Layer - DNS).
3. The request is sent using TCP for reliability (Transport Layer - TCP).
4. The request is routed using IP to reach Google's server (Internet Layer - IP).
5. Data is transmitted over Ethernet or Wi-Fi (Network Access Layer).
6. The server responds with the webpage, following the same layers in reverse.

Would you like a specific example in more detail? 😊