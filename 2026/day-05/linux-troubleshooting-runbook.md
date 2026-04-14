# Runbook

<img width="1818" height="657" alt="Picture7" src="https://github.com/user-attachments/assets/74becf0d-afe0-4826-be6c-e0dfa798c6c5" />

## Observation
**docker --version** – Confirms Docker is installed, running version 29.1.3.  
**uname -a** – Shows the system is running Linux on an Ubuntu kernel.  
**lsb_release -a** – Displays OS details, confirming it is Ubuntu 24.04 LTS.  
**cat /etc/os-release** – Provides detailed OS information including version, ID, and related URLs.  

---

<img width="1512" height="435" alt="Picture1" src="https://github.com/user-attachments/assets/1280524d-61e5-4392-a037-46c63bf5fad7" />
<img width="1446" height="84" alt="Picture2" src="https://github.com/user-attachments/assets/05cd611a-1f66-4c0b-af40-ec493dac6e36" />
## Observation
Created a directory named `runbook-demo` in `/tmp`, copied the hosts file into it, and verified the contents by listing the directory.  

---
<img width="1757" height="968" alt="Picture3" src="https://github.com/user-attachments/assets/f7ebf0b3-ea05-4a7e-8678-b85d39527375" />
<img width="1909" height="965" alt="Picture4" src="https://github.com/user-attachments/assets/61373d56-00ee-4c2e-b902-ee4ad4132d16" />
## Observation
**top** – Shows real-time CPU and memory usage, no unusual spikes, and displays active processes.  
**htop** – Processes are clearly visible with better visualization; CPU and memory usage are currently low.  

---
<img width="973" height="219" alt="Picture5" src="https://github.com/user-attachments/assets/e943ec1e-ed27-4796-a4bc-0fc7c84589f9" />

## Observation
**pgrep docker** – Shows the Docker running PID.  
**pgrep -l docker** – Displays the PID and process name (`dockerd`), confirming the Docker daemon is active.  
**ps -o pid,pcpu,pmem,comm -p 986** – Shows PID, CPU, and memory usage for the Docker daemon, indicating it is running and healthy.  

---

## Observation
<img width="1608" height="888" alt="Picture6" src="https://github.com/user-attachments/assets/7a47260a-98e1-4f70-92ef-7dd4114c61fe" />

**df -h** – Shows disk usage; the system looks healthy as the filesystem is around 42% utilized.  
**du -sh /var/log** – Displays log directory size (~44MB); some folders show “permission denied,” indicating restricted access.  
**iostat** – Indicates CPU is mostly idle (~99%) and disk I/O activity is low.  
**vmstat** – Shows low CPU usage and no swap activity, indicating efficient system performance.  

---

## Observation
<img width="1817" height="670" alt="Picture8" src="https://github.com/user-attachments/assets/b1672d8b-8c58-45b3-b240-f8c338c86547" />

**ss -tulpn** – Shows active and listening ports along with running services.  
**netstat -tulpn** – Displays network details, but limited information is shown without root privileges.  

---

## Observation
<img width="1431" height="750" alt="Picture9" src="https://github.com/user-attachments/assets/c63cc614-d966-4cdf-b515-fb8ccedc207f" />

**curl** – Downloads or fetches content from a URL.  
**ping** – Sends requests to an IP address to check reachability and shows latency.  

---

## Observation
<img width="1919" height="962" alt="Picture10" src="https://github.com/user-attachments/assets/f1e92253-49c3-4177-a98c-2b3b80bdebad" />
<img width="1919" height="468" alt="Picture11" src="https://github.com/user-attachments/assets/f6d241cc-d6bf-4dec-9df9-b75d146a7c9f" />

**journalctl** – No recent critical errors observed in Docker logs.  
**tail** – Displays the last lines of log files (e.g., from `/var/log`).  

---

## If This Worsens
- Restart Docker and check if the issue is fixed.  
- Check logs again with more details to find errors.  
- Use tools like docker inspect to debug  
