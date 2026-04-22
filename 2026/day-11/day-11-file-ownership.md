## File Ownership Challenge (chown & chgrp)

### Task 1: Understanding Ownership

- Ran `ls -l` in home directory  
- Identified owner and group columns  

**Format:**
```
-rw-r--r-- 1 owner group size date filename
```

**Observation:**
- `ubuntu` is the owner and `ubuntu` is the group for all files  
- Owner has `rwx` access  
- Group has `r-x` access  
- Others have no access  

**Difference between Owner and Group:**
- **Owner**: The user who created or owns the file  
- **Group**: A collection of users who share access permissions to the file  
<img width="947" height="215" alt="t1" src="https://github.com/user-attachments/assets/5558a34a-b175-4a56-a7c5-f19a5240326a" />


---

###  Task 2: Basic chown Operations

**Commands Used:**
```
touch devops-file.txt
ls -l devops-file.txt
sudo chown tokyo devops-file.txt
sudo chown berlin devops-file.txt
```

**Result:**
- Owner changed from `ubuntu → tokyo → berlin`  
<img width="1403" height="708" alt="t2" src="https://github.com/user-attachments/assets/5d23f6c5-7b39-4762-8de0-3d3788c50b60" />


---

###  Task 3: Basic chgrp Operations

**Commands Used:**
```
touch team-notes.txt
ls -l team-notes.txt
sudo groupadd heist-team
sudo chgrp heist-team team-notes.txt
```

**Result:**
- Group changed from `ubuntu → heist-team`  
<img width="1066" height="410" alt="t3" src="https://github.com/user-attachments/assets/a91a8e6b-4776-4b57-b3a2-3ddb4be99169" />


---

###  Task 4: Combined Owner & Group Change

**Commands Used:**
```
touch project-config.yaml
mkdir app-logs/
sudo chown professor:heist-team project-config.yaml
sudo chown berlin:heist-team app-logs/
```

**Result:**
- `project-config.yaml`: ubuntu:ubuntu → professor:heist-team  
- `app-logs/`: ubuntu:ubuntu → berlin:heist-team  

<img width="1200" height="943" alt="t4" src="https://github.com/user-attachments/assets/3156bda2-c57e-4d4a-a0a4-2099f1305944" />

---

###  Task 5: Recursive Ownership

**Commands Used:**
```
mkdir -p heist-project/vault
mkdir -p heist-project/plans
touch heist-project/vault/gold.txt
touch heist-project/plans/strategy.conf
sudo groupadd planners
sudo chown -R professor:planners heist-project/
ls -lR heist-project/
```

**Result:**
- Entire `heist-project/` directory ownership changed to:
  - Owner: professor  
  - Group: planners  

<img width="1406" height="860" alt="t51" src="https://github.com/user-attachments/assets/ee44d103-2736-420a-86b6-649279c94d74" />
<img width="1387" height="465" alt="t52" src="https://github.com/user-attachments/assets/4b497d76-2af5-4c91-89f1-4cf9225f75ab" />
<img width="1027" height="361" alt="t53" src="https://github.com/user-attachments/assets/7b6f56b3-8a70-49fb-85f9-a5c25b60d84b" />

---

###  Task 6: Practice Challenge

**Commands Used:**
```
sudo groupadd vault-team
sudo groupadd tech-team

mkdir bank-heist/
touch bank-heist/access-codes.txt
touch bank-heist/blueprints.pdf
touch bank-heist/escape-plan.txt

cd bank-heist/

sudo chown tokyo:vault-team access-codes.txt
sudo chown berlin:tech-team blueprints.pdf
sudo chown nairobi:vault-team escape-plan.txt

ls -l bank-heist/
```

**Result:**
- `access-codes.txt` → tokyo:vault-team  
- `blueprints.pdf` → berlin:tech-team  
- `escape-plan.txt` → nairobi:vault-team  

<img width="1296" height="591" alt="t6" src="https://github.com/user-attachments/assets/85eab9a2-e516-4198-88de-f662151b676f" />

---

###  Files & Directories Created

#### Directories
- app-logs  
- bank-heist  
- heist-project  
- project  

#### Files
- devops-file.txt  
- devops.txt  
- notes.txt  
- project-config.yaml  
- script.sh  
- team-notes.txt  

---

### Ownership Changes

- devops-file.txt: ubuntu → tokyo → berlin  
- team-notes.txt: ubuntu → heist-team  
- project-config.yaml: ubuntu:ubuntu → professor:heist-team  
- app-logs/: ubuntu:ubuntu → berlin:heist-team  
- heist-project/: ubuntu:ubuntu → professor:planners  
- access-codes.txt: ubuntu → tokyo, ubuntu → vault-team  
- blueprints.pdf: ubuntu → berlin, ubuntu → tech-team  
- escape-plan.txt: ubuntu → nairobi, ubuntu → vault-team  

---

### Commands Used

```
touch devops-file.txt
sudo chown tokyo devops-file.txt
sudo chown berlin devops-file.txt

touch team-notes.txt
ls -l team-notes.txt
sudo groupadd heist-team
sudo chgrp heist-team team-notes.txt

touch project-config.yaml
mkdir app-logs/
sudo chown berlin:heist-team app-logs/

mkdir -p heist-project/vault
mkdir -p heist-project/plans
touch heist-project/vault/gold.txt
touch heist-project/plans/strategy.conf

sudo groupadd planners
sudo chown -R professor:planners heist-project/

sudo groupadd vault-team
sudo groupadd tech-team

mkdir bank-heist/
touch bank-heist/access-codes.txt
touch bank-heist/blueprints.pdf
touch bank-heist/escape-plan.txt

cd bank-heist/
sudo chown tokyo:vault-team access-codes.txt
sudo chown berlin:tech-team blueprints.pdf
sudo chown nairobi:vault-team escape-plan.txt

ls -l bank-heist/
history
```
---

### What I Learned

- How to change ownership of files and directories  
- How to change group of files and directories  
- How to change both owner and group in a single command  
- How to recursively change ownership for folders and subfolders 
