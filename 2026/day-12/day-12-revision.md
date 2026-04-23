## Breather & Revision (Days 01–11)

### Processes & Services

#### Commands Practiced
- `ps`
- `systemctl status`
- `journalctl -u <service>`

#### Observations
- Checked `nginx` service status
- Confirmed that nginx is **active and running**
- Viewed active processes
- Reviewed logs using `journalctl`
<img width="1891" height="982" alt="1" src="https://github.com/user-attachments/assets/ca94b69e-84b0-4a01-95a8-71648a107d5c" />

---

### File Skills Practice

#### Commands Practiced
- `echo >>`
- `chmod`
- `chown`
- `ls -l`
- `cp`
- `mkdir`
<img width="1137" height="475" alt="2" src="https://github.com/user-attachments/assets/dc0cb907-836e-49bc-a700-b88fd11827f2" />

---

### Cheat Sheet Refresh 

#### Top 5 Commands for Incidents
1. `top` – Monitor real-time system performance  
2. `ps aux` – View all running processes  
3. `ps aux | grep <name>` – Find specific processes  
4. `kill <pid>` – Stop problematic processes  
5. `ping` – Check network connectivity  

---

### User/Group Practice

#### Scenario
- Created or modified user/group
- Verified using:
  - `id`
  - `ls -l`
<img width="1496" height="336" alt="3" src="https://github.com/user-attachments/assets/35fca1d5-6401-4b11-aef2-20c54bfe0f10" />
<img width="1442" height="576" alt="4" src="https://github.com/user-attachments/assets/e2c4c35f-9cfd-4d51-a881-be48f8eae463" />

---

### Mini Self-Check

#### Q1: Which 3 commands save you the most time and why?

- `ls -l <filename>`  
  **Why?** Previously used `ls -l` + `cd`, now can directly inspect files in one command.

- `cd <directory> | grep <filename>`  
  **Why?** Helps quickly identify files in directories with many items.

- `systemctl status <service>` & `journalctl -u <service>`  
  **Why?** First step in troubleshooting—check service status and logs.

---

#### Q2: How do you check if a service is healthy?

Commands:
- `systemctl status <service>`
- `top`
- `ps`

---

#### Q3: How do you safely change ownership and permissions?

Example:
sudo chown professor devops.txt && sudo chmod 775 devops.txt
<img width="1478" height="609" alt="5" src="https://github.com/user-attachments/assets/524aec37-298d-4ae4-9131-563f98f7cb23" />


#### Q4: Focus for the Next 3 Days
- Improve speed in command usage
- Learn how to combine commands effectively
- Practice more Linux commands
- Start preparing for interview questions
