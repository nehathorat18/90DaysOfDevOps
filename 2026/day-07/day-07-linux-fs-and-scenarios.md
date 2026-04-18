## 📁 Linux File System Hierarchy & Scenario-Based Practice



## Linux File System Hierarchy – 

### Core Directories (Must Know)

#### `/` (root) - The starting point of everything  
**Contains:** It is the top-level directory that contains all subdirectories.  
**I would use this when:** I want to see what the root directory contains and navigate to core directories.  
<img width="957" height="705" alt="1" src="https://github.com/user-attachments/assets/869a7d1a-079a-4c2c-9c02-6aec8e308b4f" />

---

#### `/home` - User home directories  
**Contains:** It contains all user home directories.  
**I would use this when:** I want to check user files, permissions, or group ownership.  
<img width="806" height="150" alt="2" src="https://github.com/user-attachments/assets/8eddc9e2-9b01-408b-948c-81965c8e5928" />

---

#### `/root` - Root user's home directory  
**Contains:** It contains the home directory of the root user.  
**I would use this when:** I want to access or manage root user files.  
<img width="962" height="315" alt="3 1" src="https://github.com/user-attachments/assets/394ce7fd-57c0-4e07-a2b6-6d33a0d24630" />

---

#### `/etc` - Configuration files  
**Contains:** It contains configuration files like hostname, systemd, crontab, etc.  
**I would use this when:** I want to check or modify system configuration files.  
<img width="1842" height="986" alt="3" src="https://github.com/user-attachments/assets/1987a17b-0931-4ff2-bf53-74405f65efdb" />

---

#### `/var/log` - Log files (very important for DevOps!)  
**Contains:** It contains log files created by the system and services.  
**I would use this when:** I want to check errors or troubleshoot system issues.  
<img width="1722" height="772" alt="4" src="https://github.com/user-attachments/assets/47b1d6f6-cb3c-4b55-980e-51c0fee1acf6" />

---

#### `/tmp` - Temporary files  
**Contains:** It contains temporary files created by the system and applications.  
**I would use this when:** I want to check or remove temporary files.  
<img width="1635" height="288" alt="5" src="https://github.com/user-attachments/assets/2c560662-f17e-4949-b834-700fe226d624" />

---

### Additional Directories

#### `/bin` - Essential command binaries  
**Contains:** It contains essential binaries like cat, ls, systemctl, etc.  
**I would use this when:** I want to run basic system commands.  
<img width="1765" height="982" alt="6" src="https://github.com/user-attachments/assets/c15afdbb-4224-4b42-a3b7-e846c6f97ef7" />

---

#### `/usr/bin` - User command binaries  
**Contains:** It contains user-level binaries like awk, chmod, chgrp, etc.  
**I would use this when:** I want to use commands to manage files or permissions.  
<img width="1857" height="991" alt="7" src="https://github.com/user-attachments/assets/808db64e-29dc-43bd-8a53-99fcbbdd6b77" />

---

#### `/opt` - Optional/third-party applications  
**Contains:** It contains third-party applications installed by the root user.  
**I would use this when:** I want to check or manage third-party applications.  
<img width="865" height="193" alt="8" src="https://github.com/user-attachments/assets/fa313023-1bd9-4f44-acca-6a6d57ae6539" />

---

### 🛠️ Hands-on Tasks 

<img width="1420" height="733" alt="9" src="https://github.com/user-attachments/assets/7ef455eb-f75f-49ef-be46-b0fff5437fd3" />

---

### Part 2: Scenario-Based Practice

#### Scenario 1: Service Not Starting

<img width="1632" height="976" alt="s1" src="https://github.com/user-attachments/assets/b22d88a4-539a-4298-9452-2626153b94a6" />

<img width="1873" height="985" alt="s12" src="https://github.com/user-attachments/assets/de85585f-09c2-4d51-a308-1a7742bba958" />

**Step 1:** systemctl status myapp  
**Why:** It shows the status of `myapp`

**Step 2:** systemctl is-enabled myapp  
**Why:** It shows whether the service is enabled or disabled.  

**Step 3:** sudo journalctl -u myapp -n 50  
**Why:** Checks logs to understand why the service failed.  

**Step 4:** sudo systemctl daemon-reload  
**Why:** Reloads systemd after configuration changes.  

**Step 5:** sudo systemctl start myapp  
**Why:** Starts the service again.  

---

#### Scenario 2: High CPU Usage

top  
htop  
ps aux --sort=-%cpu | head -10

<img width="1863" height="980" alt="s21" src="https://github.com/user-attachments/assets/f9b1af3c-a258-4c5b-ab89-dfe028be4eb2" />

<img width="1902" height="981" alt="s22" src="https://github.com/user-attachments/assets/405b8811-ad4f-4620-8af6-25733bf70c3c" />

<img width="1901" height="317" alt="s23" src="https://github.com/user-attachments/assets/33aef533-b39b-4558-8bb9-c3f45eeaf1d2" />

---

#### Scenario 3: Finding Service Logs

journalctl -u docker<br>
journalctl -u docker | tail -n 10<br>
journalctl -u docker | tail -f

<img width="1896" height="937" alt="s31" src="https://github.com/user-attachments/assets/61122544-fd87-4699-89df-84488351e3ad" />

<img width="1893" height="705" alt="s32" src="https://github.com/user-attachments/assets/5d693422-d5d9-473b-8e8b-f1555423fe2a" />

---

#### Scenario 4: File Permission Issue

ls -l /home/user/backup.sh  
chmod +x /home/user/backup.sh  
./backup.sh  

<img width="1114" height="221" alt="s41" src="https://github.com/user-attachments/assets/86a189a6-5a4f-47df-9e77-0731d11df308" />

<img width="632" height="127" alt="s42" src="https://github.com/user-attachments/assets/2421cdc4-b1f6-4332-9b36-080585f69ff0" />
