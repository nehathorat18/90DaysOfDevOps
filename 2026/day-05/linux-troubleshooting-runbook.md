# 🛠️ Runbook

---

## Environment Basics

<img width="1818" height="657" alt="Environment" src="https://github.com/user-attachments/assets/74becf0d-afe0-4826-be6c-e0dfa798c6c5" />

**docker --version** – Confirms Docker is installed, running version 29.1.3.  
**uname -a** – Shows the system is running Linux on an Ubuntu kernel.  
**lsb_release -a** – Displays OS details, confirming it is Ubuntu 24.04 LTS.  
**cat /etc/os-release** – Provides detailed OS information including version, ID, and related URLs.  

---

##  Filesystem Sanity

<img width="1512" height="435" alt="FS1" src="https://github.com/user-attachments/assets/1280524d-61e5-4392-a037-46c63bf5fad7" />
<img width="1446" height="84" alt="FS2" src="https://github.com/user-attachments/assets/05cd611a-1f66-4c0b-af40-ec493dac6e36" />

Created a directory named `runbook-demo` in `/tmp`, copied the hosts file into it, and verified the contents by listing the directory.  

---

## CPU / Memory

<img width="1757" height="968" alt="CPU1" src="https://github.com/user-attachments/assets/f7ebf0b3-ea05-4a7e-8678-b85d39527375" />
<img width="1909" height="965" alt="CPU2" src="https://github.com/user-attachments/assets/61373d56-00ee-4c2e-b902-ee4ad4132d16" />

**top** – Shows real-time CPU and memory usage, no unusual spikes, and displays active processes.  
**htop** – Provides better visualization; CPU and memory usage are currently low.  

---

## Process Check (Docker)

<img width="973" height="219" alt="Process" src="https://github.com/user-attachments/assets/e943ec1e-ed27-4796-a4bc-0fc7c84589f9" />

**pgrep docker** – Shows the Docker running PID.  
**pgrep -l docker** – Displays the PID and process name (`dockerd`), confirming the Docker daemon is active.  
**ps -o pid,pcpu,pmem,comm -p 986** – Shows PID, CPU, and memory usage for Docker, indicating it is healthy.  

---

##  Disk / IO

<img width="1608" height="888" alt="Disk" src="https://github.com/user-attachments/assets/7a47260a-98e1-4f70-92ef-7dd4114c61fe" />

**df -h** – Disk usage looks healthy (~42% used).  
**du -sh /var/log** – Log size is ~44MB; some folders show “permission denied.”  
**iostat** – CPU mostly idle (~99%), low disk I/O.  
**vmstat** – Low CPU usage and no swap activity.  

---

##  Network

<img width="1817" height="670" alt="Network" src="https://github.com/user-attachments/assets/b1672d8b-8c58-45b3-b240-f8c338c86547" />

**ss -tulpn** – Shows active and listening ports with services.  
**netstat -tulpn** – Displays network details (limited without root access).  

---

## Connectivity Check

<img width="1431" height="750" alt="Connectivity" src="https://github.com/user-attachments/assets/c63cc614-d966-4cdf-b515-fb8ccedc207f" />

**curl** – Fetches content from a URL.  
**ping** – Checks if an IP is reachable and shows latency.  

---

##  Logs

<img width="1919" height="962" alt="Logs1" src="https://github.com/user-attachments/assets/f1e92253-49c3-4177-a98c-2b3b80bdebad" />
<img width="1919" height="468" alt="Logs2" src="https://github.com/user-attachments/assets/f6d241cc-d6bf-4dec-9df9-b75d146a7c9f" />

**journalctl** – No recent critical errors in Docker logs.  
**tail** – Displays the latest lines from log files.  

---

##  If This Worsens

- Restart Docker and check if the issue is fixed.  
- Check logs again with more details to find errors.  
- Use tools like `docker inspect` to debug further.  
