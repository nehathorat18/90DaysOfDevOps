## Networking Concepts: DNS, IP, Subnets & Ports

### Task 1: DNS – How Names Become IPs

#### Explain in 3–4 lines: what happens when you type google.com in a browser?

When I type google.com, my system first finds its IP address using DNS. Then it connects to that server over the internet. My browser sends a request and the server sends back the webpage. Finally, the page appears on my screen.

---

#### What are these record types? Write one line each:

- A — Maps a domain name to an IPv4 address
  <img width="1147" height="618" alt="1" src="https://github.com/user-attachments/assets/eec92909-42a9-474e-91bc-0067d040f54a" />

- AAAA — Maps a domain name to an IPv6 address
  <img width="1105" height="607" alt="2" src="https://github.com/user-attachments/assets/0d9b64b2-5032-4203-acc9-d49c77626adc" />

- CNAME — Maps a domain name to another domain name
<img width="1484" height="487" alt="3" src="https://github.com/user-attachments/assets/9b179213-8695-4f91-92d5-67c290148c60" />
  
- MX — Specifies mail servers responsible for receiving emails for a domain
- <img width="1338" height="547" alt="4" src="https://github.com/user-attachments/assets/f765f5a8-a236-4384-b954-e97d2b9972a2" />

- NS — Specifies the authoritative name servers for a domain  
<img width="1155" height="995" alt="5" src="https://github.com/user-attachments/assets/e00ab280-f65e-4e48-af18-0de3e04af924" />

---

#### Run: dig google.com — identify the A record and TTL from the output
<img width="880" height="558" alt="6" src="https://github.com/user-attachments/assets/b993c44f-5504-49f7-80fa-d501219c3b13" />

---

### Task 2: IP Addressing

#### What is an IPv4 address? How is it structured? (e.g., 192.168.1.10)

An IPv4 address is a unique number given to a device on a network by an ISP so it can communicate with other devices on the internet or a local network.Each number ranges from 0 to 255.

| Octet | Decimal | Binary     |
|------|---------|------------|
| 1    | 192     | 11000000   |
| 2    | 168     | 10101000   |
| 3    | 1       | 00000001   |
| 4    | 10      | 00001010   |

---

#### Difference between public and private IPs — give one example of each

- Public — It is visible to all other networks or devices  
- Private — It is visible only to you and your local network  

---

#### What are the private IP ranges?

- 10.0.0.0 – 10.255.255.255  
- 172.16.0.0 – 172.31.255.255  
- 192.168.0.0 – 192.168.255.255  

---

#### Run: ip addr show — identify which of your IPs are private
<img width="1182" height="346" alt="7" src="https://github.com/user-attachments/assets/6d5e362e-68fb-44ba-9e48-d1a93b82b90f" />
<img width="1858" height="252" alt="8" src="https://github.com/user-attachments/assets/2060c3ad-df37-4459-9e32-10d12d477b97" />

---

### Task 3: CIDR & Subnetting

#### What does /24 mean in 192.168.1.0/24?

/24 means CIDR notation specifies network bits.

---

#### How many usable hosts in a /24? A /16? A /28?
| CIDR | Usable Hosts |
|------|--------------|
| /24  | 254          |
| /16  | 65,534       |
| /28  | 14           |
---

#### Explain in your own words: why do we subnet?

Divide our network into sub-parts.

---

#### Quick exercise — fill in:

| CIDR | Subnet Mask       | Total IPs | Usable Hosts |
|------|------------------|-----------|--------------|
| /24  | 255.255.255.0    | 256       | 254          |
| /16  | 255.255.0.0      | 65,536    | 65,534       |
| /28  | 255.255.255.240  | 16        | 14           |

---

### Task 4: Ports – The Doors to Services

#### What is a port? Why do we need them?

It is a rule that helps us route data correctly to the correct application.

---

#### Document these common ports:

| Port  | Service  |
|------|----------|
| 22   | SSH      |
| 80   | HTTP     |
| 443  | HTTPS    |
| 53   | DNS      |
| 3306 | MySQL    |
| 6379 | Redis    |
| 27017| MongoDB  |

---

### Task 5: Putting It Together

#### 1. curl http://myapp.com:8080 – networking concepts involved

- DNS: Resolve myapp.com → IP  
- TCP: Reliable transport layer  
- HTTP: Application protocol  
- Port 8080: Directs request to a specific service  

---

#### 2. Database connectivity issue

If the app can't reach 10.0.1.50:3306:

- Check network connectivity: ping 10.0.1.50  
- Check firewall rules: Ensure port 3306 is open  
- Check database service: MySQL must be running and listening on 3306  

---

### What I Learned
- I learned how to troubleshoot issues.
- DNS is important, so it should be checked first.
- Public and private IPs, CIDR and subnet masks help manage networks and calculate usable hosts.
