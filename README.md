# Task 5: Capture and Analyze Network Traffic Using Wireshark  

**Author:** Kush Thaker  
**Email:** kthaker442@gmail.com  

---

## Overview  
This task involves capturing and analyzing network traffic using Wireshark on a Kali Linux system. The process included identifying the operating system, capturing packets on the active network interface, filtering by protocol, and analyzing multiple protocols such as TCP, HTTP, and DNS.  

---

## Steps Performed  

### Step 0: Identifying OS  
- Booted into **Kali Linux OS** to perform the task.  

### Step 1–5: Capturing Network Traffic  
- Used Wireshark on the active interface **wlan0**.  
- Browsed websites and pinged servers to generate traffic.  
- Applied filters for **TCP, HTTP, and DNS protocols**.  
- Captured traffic for **2–2.5 minutes** and saved it as `tasks.pcap`.  

---

## Protocols Analyzed  

### 1. TCP (Transmission Control Protocol)  
- Observed the **3-way handshake (SYN, SYN/ACK, ACK)**.  
- Data transfer packets included `[PSH, ACK]` and retransmissions.  
- Connection termination observed with **FIN, ACK**.  

**Example Packet:**  
```
Source: 2409:40c1:308a:1d87...  
Destination: 2404:6800:4002:819... (Google server IPv6)  
Info: TCP 94 53812 → 443 [SYN] Seq=0 Win=64800 Len=0 MSS=1440
```

**Key Point:** TCP ensures reliable, ordered packet delivery.  

---

### 2. HTTP (Hypertext Transfer Protocol)  
- Captured **plain HTTP requests and responses**.  
- Observed requests like `GET /success.txt?ipv4 HTTP/1.1`.  
- Server responses included `HTTP/1.1 200 OK`.  

**Example Packet:**  
```
Source: 192.168.31.50  
Destination: 34.107.221.82  
Info: GET /success.txt?ipv4 HTTP/1.1
```

**Key Point:** HTTP is used for retrieving web resources.  

---

### 3. DNS (Domain Name System)  
- Queries sent to **Google DNS (8.8.8.8)**.  
- Lookups for domains like `www.google.com`, `www.youtube.com`, `fonts.googleapis.com`.  
- Both **A (IPv4)** and **AAAA (IPv6)** records captured.  

**Example Packet:**  
```
Source: 192.168.31.50  
Destination: 8.8.8.8  
Info: Standard query 0x8742 AAAA o.pki.goog CNAME pki-goog.l.google.com
```

**Key Point:** DNS resolves domain names into IP addresses before communication.  

---

### 4. TLS (Transport Layer Security) *(optional, but visible)*  
- Detected **TLSv1.2 and TLSv1.3 encrypted traffic**.  
- Observed packets like **Client Hello** and **Application Data**.  

**Key Point:** Confirms secure HTTPS communication.  

---

## Step 7: Exported Capture  
- Capture saved as **`task5.pcap`** in this repository’s main branch.  

---

## Step 8: Summary of Findings  
- TCP provided reliable communication via the handshake process.  
- HTTP requests and responses confirmed successful data transfers.  
- DNS resolved multiple domains into corresponding IPs.  
- TLS confirmed encrypted sessions for secure browsing.  

---

## Additional Notes  
- **Screenshots** of the process and analysis are available in the **`images/` folder** of this repository.  
- For a more detailed explanation and full analysis, please refer to **`Task5Report.pdf`**.  

---

**Thank You,**  
Kush Thaker  
