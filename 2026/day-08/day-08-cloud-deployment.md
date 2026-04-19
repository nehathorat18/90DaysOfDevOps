## Cloud Server Setup: Docker, Nginx & Web Deployment

---

### Part 1: Launch Cloud Instance & SSH Access 

#### Step 1: Create a Cloud Instance
<img width="1907" height="853" alt="1" src="https://github.com/user-attachments/assets/26d8424d-26ce-46fa-b68e-3220509ee037" />

---

#### Step 2: Connect via SSH
<img width="1437" height="992" alt="2" src="https://github.com/user-attachments/assets/2acb28cf-539f-475b-98f4-c035c6336a2f" />

---

### Part 2: Install Docker & Nginx 

#### Step 1: Update System
sudo apt-get update  
sudo apt-get upgrade  

---

#### Step 2: Install Nginx & Docker
sudo apt-get install nginx  
sudo apt-get install docker.io  

---

#### Step 3: Verify Services
systemctl status nginx  
systemctl status docker  

---

### Part 3: Security Group Configuration

#### Test Web Access
Open browser and visit:

http://100.55.25.34/

<img width="1912" height="958" alt="nginx-webpage" src="https://github.com/user-attachments/assets/3e05dad4-05bf-43b8-9873-15024deb5404" />

---

### Part 4: Extract Nginx Logs 

#### Step 1: View Nginx Logs
sudo cat /var/log/nginx/access.log

#### Step 2: Save Logs to File
sudo cat /var/log/nginx/access.log > nginx-logs.txt

#### Step 3: Download Log File to Your Local Machine
scp -i first_key.pem ubuntu@ec2-100-55-25-34.compute-1.amazonaws.com:~/nginx-logs.txt .

---

### Commands Used

1. sudo apt-get update  
2. sudo apt-get upgrade  
3. sudo apt-get install nginx  
4. sudo apt-get install docker.io  
5. systemctl status nginx  
6. systemctl status docker  
7. sudo cat /var/log/nginx/access.log  
8. scp -i first_key.pem ubuntu@ec2-100-55-25-34.compute-1.amazonaws.com:~/nginx-logs.txt .

---

### Challenges Faced

- Page not accessible: HTTP port 80 access was not allowed.

---

### What I Learned

- How to deploy a real web server on the cloud  
- The importance of checking inbound rules before deploying a server  
- How to copy and download logs for troubleshooting  

---
