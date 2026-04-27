## Networking Fundamentals & Hands-on Checks


### OSI layers (L1–L7) vs TCP/IP stack (Link, Internet, Transport, Application)

The OSI model has 7 layers, starting from the application layer at the top to the physical layer at the bottom. It is a theoretical model that explains how data flows through different layers in a network.

The TCP/IP model is the practical version. It has 4 layers: application, transport, internet, and network access and its used in real-world networking to transfer data.

---

## OSI Model vs TCP/IP Model

| Layer | OSI Model     | TCP/IP Model   | Purpose                                           |
|------|---------------|----------------|--------------------------------------------------|
| 7    | Application   | Application    | User-level protocols like HTTP, SSH, DNS         |
| 6    | Presentation  | Application    | Data formatting, encryption                      |
| 5    | Session       | Application    | Managing sessions between apps                   |
| 4    | Transport     | Transport      | TCP (used for browsing), UDP (used for streaming media) |
| 3    | Network       | Internet       | IP addressing and routing                        |
| 2    | Data Link     | Network Access | MAC addresses                                    |
| 1    | Physical      | Network Access | Cables, hardware, signals                        |

---

## Where IP, TCP/UDP, HTTP/HTTPS, DNS sit in the stack

- IP → Internet  
- TCP/UDP → Transport  
- HTTP/HTTPS → Application  
- DNS → Application  

---

### One real example

`curl https://example.com` = Application layer over TCP over IP

<img width="1787" height="555" alt="1" src="https://github.com/user-attachments/assets/18b2a2a7-2900-4ad6-aa58-11aa9e1f78c6" />

---

- **Identity:** `hostname -I` (or `ip addr show`) — note your IP.  
<img width="1377" height="423" alt="2" src="https://github.com/user-attachments/assets/3ac402e9-b4ab-4112-99b6-b3c5b4216afb" />

---

- **Reachability:** `ping <target>` — mention latency and packet loss.  
<img width="1328" height="476" alt="3" src="https://github.com/user-attachments/assets/0a243e85-49de-46a5-aa11-5b0bd864b6e4" />

---

- **Path:** `traceroute <target>` (or `tracepath`) — note any long hops/timeouts.  
<img width="1792" height="523" alt="4" src="https://github.com/user-attachments/assets/abb574e3-09a6-42d9-8e52-2a312c3bc412" />

---

- **Ports:** `ss -tulpn` (or `netstat -tulpn`) — list one listening service and its port.  
<img width="1826" height="642" alt="5" src="https://github.com/user-attachments/assets/e0659328-e0cb-4724-886c-6699f04b2c49" />

---

- **Name resolution:** `dig <domain>` or `nslookup <domain>` — record the resolved IP.  
<img width="1213" height="873" alt="6" src="https://github.com/user-attachments/assets/e993a7c3-7eb9-40cd-b81a-3c4e9d3e9648" />

---

- **HTTP check:** `curl -I <http/https-url>` — note the HTTP status code.  
<img width="1908" height="303" alt="7" src="https://github.com/user-attachments/assets/cbfd45fa-580f-433a-a60d-6c44ccb72d3d" />

---

- **Connections snapshot:** `netstat -an | head` — count ESTABLISHED vs LISTEN (rough).  
<img width="1167" height="262" alt="8" src="https://github.com/user-attachments/assets/17eb69a8-3664-4cc3-8653-98f88552a1b4" />

---

### Mini Task: Port Probe & Interpret

Identify one listening port from `ss -tulpn` (e.g., SSH on 22 or a local web app).  

From the same machine, test it:  
`nc -zv localhost <port>` (or `curl -I http://localhost:<port>`)

<img width="1863" height="291" alt="9" src="https://github.com/user-attachments/assets/c52387bc-e8db-42fb-aec6-57918dd94662" />

Write one line: Is it reachable? If not, what’s the next check? (e.g., service status, firewall).

Result: Connection successful. If not reachable:  
Next checks: `systemctl status ssh`

---

### Which command gives you the fastest signal when something is broken?

PING

---

### What layer (OSI/TCP-IP) would you inspect next if DNS fails? If HTTP 500 shows up?

**If DNS fails (name resolution problem):**  
I'll check the Application layer (OSI/TCP-IP), as it is an application layer protocol. If unresolved, move to the Transport layer.

**If HTTP 500 shows up (application logic/server issue):**  
I'll check the Application layer (OSI/TCP-IP). HTTP 500 indicates an application logic/server issue.

---

### Two follow-up checks you’d run in a real incident

DNS issue → `dig` / `nslookup`  
HTTP 500 → Check server logs and use `curl` command

---
